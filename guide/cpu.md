# The CPU

<p align="center">
  <br />
  <img width="460" height="300" src="https://www.pcworld.com/wp-content/uploads/2021/10/intel-cpu-rocket-lake-rear.jpg?quality=50&strip=all&w=1024">
  <br />
  <span>just a placeholder image to break up the content!</span>
</p>

Have you heard of the companies Intel or AMD? These are two popular companies that manufacture the CPUs that go into our computers. All of the computers we use contain something called a central processing unit, also known as the CPU or the processor, which effectively acts as the brain of the computer.

Computers contain other processing units (like the graphics card!) that are responsible for processing other more specific things, but the CPU is your general powerhouse for all computing tasks. That being said, the CPU can do shockingly little: it can **read values**, **set values**, and **perform simple math** calculations like addition and subtraction.

You hand it numbers, and it’s put to work crunching the data however you’d like. That's it. Everything your computer doing is made up of just that. Isn't that wild?

## The Instruction Cycle

When we ask the CPU to do something, we do that by way of an **instruction**. We say something like, hey CPU - can you add these two numbers together? When the CPU sees that instruction, it sets off a a cycle with 3 main stages:

1. [**Fetch**](#fetch) the data from memory
1. [**Decode**](#decode) that data to understand the instruction
1. [**Execute**](#execute) the instruction

<p align="center">
  <br />
  <img width="1000" src="https://cloud-p921tgnwf-hack-club-bot.vercel.app/0v2__3_.png">
  <br />
  <span>just a placeholder image to break up the content!</span>
</p>

### Fetch

In the first phase of the pipeline, the CPU must fetch data from memory. Memory, also known as random access memory or **RAM**, is a type of short term storage your computer has. There are longer term storage places, like your hard drive, but we use memory when we need to keep something around temporarily.

<p align="center">
  <br />
  <img width="460" height="300" src="https://img.freepik.com/free-photo/warehouse-with-cardboard-boxes-inside-pallets-racks-logistic-center-huge-large-modern-warehouse-warehouse-filled-with-cardboard-boxes-shelves-boxes-stand-pallets-3d-illustration_92790-1630.jpg?w=2000">
  <br />
  <span>just a placeholder image to break up the content!</span>
</p>

Keeping with our warehouse metaphor, accessing your RAM is kind of like going to a storage rack with boxes. Each piece of data (boxes, in our metaphor) has an "address" (box location) where you can view the contents (what's inside the box!). You can also clear out the contents (take the box off of the spot on the rack), and then store new pieces of data (add new boxes to the rack).

Here's something wild for you: in the CPU, our boxes are actually just _electrical currents_. And because we store data as electricity, when your computer turns off and no more electricity is traveling to it, all of the things you have stored get cleared out! It’s kind of like if every night when the warehouse closed, all of the packages are got thrown out. That’s why we refer to it as short term memory - we want to make sure to store important things in the hard drive, which is our longer term storage, lest it be thrown away.

Our RAM, or box racks, has quite a bit of room to store our things - enough to hold large boxes. But, moving large boxes around the warehouse can be slow and cumbersome. So, for faster, smaller, and temporary storage, we have a set of numbered cubbyholes along the floor of the warehouse where we can place smaller packages. Those are our **registers**.

<p align="center">
  <br />
  <img width="460" height="300" src="https://img.directindustry.com/images_di/photo-mg/4846-14967817.jpg">
  <br />
  <span>just a placeholder image to break up the content!</span>
</p>

Registers are where the CPU can store small pieces of data so that it can keep interacting with them. For example, let’s say we need to add two numbers together.

First, the CPU retrieves the first number it needs for the equation. Since the CPU can really only do one thing at a time, it needs to put this number down in order to grab the next number. So it stores this first number into a register for the time being.

Next, the CPU grabs the second number in the equation. The CPU now has all the information it needs to add the two numbers together. It goes ahead and executes the adding instruction, passing that new number along, and then moves on to the next instruction it’s given!

The CPU keeps track of which instruction it's fetching data for with a special register called the **program counter**. The program counter contains the address of the instruction currently being executed. And in most cases, after an instruction is executed, the program counter needs to increment itself by `1` to point to the next instruction address.

Now you may be asking yourself - why don’t we store everything in the registers, since memory is slower? Well, we only have a limited amount of space in our registers. The actual size depends on your computers hardware. Depending on the particular processor, you may get around 16 general purpose registers to store your data in. There are more registers than that, but some registers are used internally and can’t be directly accessed.

Memory can easily hold over _15 million times_ the amount that registers can! Since computers have to process so much data, we can very quickly run out of space in our registers. So any data that we don't need to actively use for an instruction, we place in memory.

### Decode

Now that we've fetched the data, what does that data actually look like? Well, like we've said before, **everything is just numbers**. But what those numbers represent include five broad categories:

1. Instructions (like `ADD`)
1. Numbers
1. Letters (displayed as [ASCII](#bytes-&-ascii))
1. Register addresses
1. Memory addresses

The CPU will distinguish what type of data it is when it gets to this decoding step.

Each CPU has a set of instructions that is built _physically into the chip_, which you can think of as a list of actions that coordinate with numbers that the CPU can do. Since the data grabbed from the fetch phase is just numbers, the CPU can decode the instruction by comparing the number it sees to the set instructions list.

The first part of the data it fetches is the opcode, which is the unique identifier for an action that the CPU can run (like `ADD`).

The next numbers that are fetched are the arguments to be executed. For a very hypothetical example, let's take instruction `ADD 3 4`. Our opcode is `ADD`, and our arguments are `3` and `4`!

### Execute

After the data fetched is decoded, the CPU now has an instruction that it will execute.

If the instruction is an arithmetic (like adding or subtracting) or logical (like comparing two digits to give a true or false) instruction, it has an extra step of being sent to something called the **arithmetic-logic unit**, or **ALU**, which is made from a series of [logic gates](#boolean-logic). The ALU would then return a value, which is stored in a register until an instruction needs it.

### Modern Day

Nowadays, instead of a cycle where each flow of instruction ends before the next one starts, CPUs implement a something called **pipelining**.

Imagine a warehouse where we are packing boxes. The CPU is the warehouse, and each station (the adding of items, packaging, and loading into vans) is a step in processing instructions (the packages).

In the simpler cycle method described above, one package would be fully packed and shipped before the next one is worked on.

Alternatively, pipelining would use an assembly line where a package could go through a single station. Once it finishes and moves to the next station, a new package arrives at this station! Before our first package is shipped, other packages have already starting to be filled and packed.

What this means in for us in CPU terms is that modern CPUs can simultaneously fetch, decode, and execute different instructions _at the same time_. This dramatically cuts down on execution time, which allows the CPU to operate much faster! Yay for us!

<br>

---

<a href="/guide/introduction.md">
  <img align="left" width="70" src="https://cloud-cirb9mt0l-hack-club-bot.vercel.app/0screen_shot_2022-05-31_at_2.40.40_pm.png" />
</a>

<p align="right">
  <em>
    <b>
      <a href="/guide/physical-world.md">
        Translating this to the physical world →
      </a>
    </b>
  </em>
</p>
