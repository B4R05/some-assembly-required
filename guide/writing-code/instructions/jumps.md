# Jumping For Joy

Assembly code executes sequentially, meaning that after executing an instruction, the computer moves to the next instruction to execute. The computer is able to keep track of which line of code it's executing with something called **the instruction pointer**.

## The Instruction Pointer

The CPU has many specialized registers, which we don't access directly. One of them is the **instruction pointer** (referenced as `rip`), also known as the **program counter**.

When an assembly program is ran, each instruction is stored into memory next to each other.

The instruction pointer register stores the **memory address** of the current line of the program it's executing, and updates itself automatically.

For example, let's say we're running an assembly program that has an instruction for adding two numbers together. Once that instruction finishes running, the instruction pointer increments to point at the next instruction of the program.

For x86-64 machines that are 64-bit, that would mean that each time an instruction finishes, the instruction pointer adds 8. This is because, as you may remember, 64 bits is 8 bytes (64 bits / 8 bits per byte = 8 bytes). Each memory address represents a byte of data. Each instruction is stored as 8 bytes.

So let's say our first instruction is at memory address `0x00000001`. If we incremented to `0x00000002`, that would be **1 byte** of data, or **8 bits**. If we want to increment by an instruction's amount of data (**8 bytes**), we'd increment to `0x00000009`, since that's 8 bytes after `0x00000001`.

_Insert drawn diagram of a program, its memory address next to it, and showing the instruction pointer_

---

Remember how I said we don't access the instruction pointer directly? That stands true, however we can change where the instruction pointer is pointing with a jump instruction.

```asm
; X86-64 Intel Syntax Assembly

mov rcx, 10
jmp .addNumbers
sub rcx, 11 ; This line will be skipped since we are jumping to .addNumbers

.addNumbers
  mov rax, 3
  mov rbx, 1
  add rax, rbx
```

<br />

`.addNumbers` is a **label**. When assembled to machine code, labels assemble to memory addresses that point to the first instruction after the label.

In our example, when the program sees the `jmp` instruction, the instruction pointer would update so that it points to the line after `.addNumbers`, which is `mov rax, 3`.

_Insert drawn diagram of a jmp, its memory address next to it, and showing the instruction pointer_

## Conditionals



### Flags



<br />

---

<a href="/guide/writing-code/registers.md">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://cloud-5aq8uo1rv-hack-club-bot.vercel.app/0backd.png">
    <img align="left" width="60" src="https://cloud-5v3nvbscw-hack-club-bot.vercel.app/0backl.png" />
  </picture>
</a>

<p align="right">
  <em>
    <b>
      <a href="/guide/writing-code/instructions/math.md">
        What else can we do? →
      </a>
    </b>
  </em>
</p>
