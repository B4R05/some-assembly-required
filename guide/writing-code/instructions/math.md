# In Addition

Let's do a little bit of math. I swear it won't be bad!!

First, we'll talk about the `add` instruction.

```js
// JavaScript
let a = 3;
a = a + 1;
```
_In JavaScript, we're adding `1` to the contents of the variable `a`. At the end of this, `a` will contain the value `4`._

```asm
; X86-64 Assembly
mov rax, 3;
add rax, 1;
```
_In assembly, we're adding `1` to the contents of the register `rax`. At the end of this, `rax` will contain the value `4`._

The `add` instruction adds the value on the right side (`1`) to the contents of the register on the left side (`rax`, which contains `3`). It then takes the sum of these two numbers and, like our `mov` instruction, stores the value _into_ the register on the left side (`rax`).

---

Just like our `mov` instruction, the `add` instruction can use the contents of second register to operate on the first register.

```js
// JavaScript
let a = 3;
let b = 1;

a = a + b;
```
_In JavaScript, we're adding the contents of `b` to the contents of `a`. At the end of this, `a` will contain the value `4`._

```asm
; X86-64 Assembly
mov rax, 3;
mov rbx, 1;

add rax, rbx;
```
_In assembly, we're adding the contents of `rbx` to the contents of `rax`. At the end of this, `rax` will contain the value `4`._

---

Subtraction works the same way as addition!

```js
// JavaScript
let a = 3;
let b = 1;

a = a - b;
```
_In JavaScript, we're minusing the contents of `b` from the contents of `a`. At the end of this, `a` will contain the value `2`._

```asm
; X86-64 Assembly
mov rax, 3;
mov rbx, 1;

sub rax, rbx;
```
_In assembly, we're minusing the contents of `rbx` from the contents of `rax`. At the end of this, `rax` will contain the value `2`._

`sub` subtracts the value on the right side (`1`) _from_ the contents (`3`) of the register (`rax`) on the left side.

<br />

---

<a href="/guide/writing-code/instructions/mov.md">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://cloud-5aq8uo1rv-hack-club-bot.vercel.app/0backd.png">
    <img align="left" width="60" src="https://cloud-5v3nvbscw-hack-club-bot.vercel.app/0backl.png" />
  </picture>
</a>

<p align="right">
  <em>
    <b>
      <a href="/guide/writing-code/instructions/.md">
         →
      </a>
    </b>
  </em>
</p>
