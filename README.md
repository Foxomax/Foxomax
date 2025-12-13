<h1 align="center">Hi 👋, I'm Foxomax</h1>
<h3 align="center">A passionate fullStack developer from Nicaragua :D</h3>

```
; 6502 Assembly - Profile Initialization
.org $8000              ; ROM Start Vector

RESET:
    LDX #$00            ; Initialize X index register
    SEI                 ; Disable interrupts during render

WRITE_LOOP:
    LDA DEV_ID, X       ; Load byte from profile data
    BEQ LISTEN          ; If 0 (null terminator), jump to main loop
    STA $0400, X        ; Store byte in Screen RAM (Video Matrix)
    INX                 ; Increment index
    JMP WRITE_LOOP      ; Continue loop

LISTEN:
    JMP LISTEN          ; Infinite loop (awaiting input)

DEV_ID:
    .byte "Foxomax", 0  ; Null-terminated string
```

I love the low level programming.

