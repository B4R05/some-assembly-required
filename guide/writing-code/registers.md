# Registers

Now that we know about data, we should talk about storing data. In our brief mention of registers previously, we learned that registers are for storing data temporarily for later use.

In programming, you'd use a variable to store data for later use. You can think of registers as the variables of assembly language.

We'll be talking about the **x86-64** registers here, but the concepts apply to other processors as well.

<p align="center">
  <br />
  <img height="600" src="https://cloud-1dple0n1y-hack-club-bot.vercel.app/0screen_shot_2022-06-01_at_10.49.40_am.png">
  <br />
  <span>
    <em>
      Commonly used registers from <a href="https://web.stanford.edu/class/archive/cs/cs107/cs107.1222/guide/x86-64.html">Stanford CS107</a>
    </em>
  </span>
</p>
<br />

There are a few registers to choose from, and each one of them has a convention set up for how to use it. Some of the registers are general purpose, meaning you can store whatever you need to there while your program is executing. But there are also some specialized registers that are used for specific data, like [the instruction pointer](#the-instruction-pointer) or [the stack pointer](#the-stack-pointer), which we will talk about below.

## Register data

As we learned earlier, the only things we can store in our registers are numbers, since a computer can only understand numbers.

The data saved in registers are:
1. Numbers (`10`)
1. Letters (`c`)
1. Memory addresses (`0x12345678`)

The computer stores those numbers as [bits](/guide/writing-code/data.md), and the amount of bits a register can hold depends on the processor.

Have you heard of **32-bit** or **64-bit**? That's referring to the size of the registers in the processor! So a 64-bit processor has twice the room in a single register as 32-bit processors, which looks like:

```
0000101011111000011000110101000100001010111110000110001101010001
```

Whereas 32 bit would be:

```
000010101111100001100011010100
```

There are x86 processors that are 16-bit, 32-bit, and 64-bit, so we specify the "-64" in "x86-64" to know we're talking about the 64-bit version. You'll see some examples online that use the 32-bit version, and the registers they refer to are different. Usually 32-bit registers start with the letter `E`, whereas 64-bit registers usually start with the letter.

Since a register holds **64 bits**, that can also be translated to **8 bytes** (64 _(bits)_ divided by 8 _(bits in a byte)_).

Just like we have **bytes** to refer to groups of **bits**, we have **words** to refer to groups of **bytes**.

- A **single word** is **2 bytes**, which is 16 bits (2 _(bytes)_ multiplied by 8 _(bits per byte)_).

- A **double word** is **4 bytes**, which is 32 bits (4 _(bytes)_ multiplied by 8 _(bits per byte)_).

- A **quadruple word** is **8 bytes**, which is 64 bits (8 _(bytes)_ multiplied by 8 _(bits per byte)_).

So, another way to refer to the register size is as a quadruple word, or **qword**.

<br />

---

<a href="/guide/writing-code/data.md">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://cloud-5aq8uo1rv-hack-club-bot.vercel.app/0backd.png">
    <img align="left" width="60" src="https://cloud-5v3nvbscw-hack-club-bot.vercel.app/0backl.png" />
  </picture>
</a>

<p align="right">
  <em>
    <b>
      <a href="/guide/writing-code/writing-code.md">
        Let's boss this computer around →
      </a>
    </b>
  </em>
</p>
