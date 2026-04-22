
# Exercício 1:
```
; Questão 01

section .data
    msg_x db "Digite x: ", 0
    msg_y db "Digite y: ", 0

    msg_soma db "Soma: ", 0
    msg_sub db "Diferenca: ", 0
    msg_mul db "Produto: ", 0
    msg_div db "Quociente: ", 0
    msg_res db "Resto: ", 0

    newline db 10

section .bss
    x resq 1
    y resq 1
    buffer resb 32

section .text
    global _start

_start:

    mov rax, 1
    mov rdi, 1
    mov rsi, msg_x
    mov rdx, 10
    syscall

    mov rax, 0
    mov rdi, 0
    mov rsi, buffer
    mov rdx, 32
    syscall

    call str_to_int
    mov [x], rax

    mov rax, 1
    mov rdi, 1
    mov rsi, msg_y
    mov rdx, 10
    syscall

    mov rax, 0
    mov rdi, 0
    mov rsi, buffer
    mov rdx, 32
    syscall

    call str_to_int
    mov [y], rax

    mov rax, [x]
    add rax, [y]
    call print_result
    mov rsi, msg_soma
    call print_label

    mov rax, [x]
    sub rax, [y]
    call print_result
    mov rsi, msg_sub
    call print_label

    mov rax, [x]
    mov rbx, [y]
    mul rbx
    call print_result
    mov rsi, msg_mul
    call print_label

    mov rax, [x]
    mov rbx, [y]
    xor rdx, rdx
    div rbx
    push rdx
    call print_result
    mov rsi, msg_div
    call print_label

    pop rax
    call print_result
    mov rsi, msg_res
    call print_label

    mov rax, 60
    xor rdi, rdi
    syscall

str_to_int:
    xor rax, rax
    xor rcx, rcx

.loop:
    mov bl, [buffer + rcx]
    cmp bl, 10
    je .done

    sub bl, '0'
    imul rax, rax, 10
    add rax, rbx

    inc rcx
    jmp .loop

.done:
    ret


int_to_str:
    mov rcx, 0
    mov rbx, 10

.loop2:
    xor rdx, rdx
    div rbx
    add rdx, '0'
    push rdx
    inc rcx
    test rax, rax
    jnz .loop2

.print:
    pop rax
    mov [buffer], al

    mov rax, 1
    mov rdi, 1
    mov rsi, buffer
    mov rdx, 1
    syscall

    loop .print
    ret


print_label:
    mov rax, 1
    mov rdi, 1
    mov rdx, 15
    syscall
    ret

print_result:
    push rax
    mov rsi, rax
    call int_to_str

    mov rax, 1
    mov rdi, 1
    mov rsi, newline
    mov rdx, 1
    syscall

    pop rax
    ret
```

# Exercício 2:
```
section .data
    msg_x db "Digite x: ", 0
    msg_y db "Digite y: ", 0

    msg_rx db "Novo x: ", 0
    msg_ry db "Novo y: ", 0

    newline db 10

section .bss
    x resq 1
    y resq 1
    buffer resb 32

section .text
    global _start

_start:

    mov rax, 1
    mov rdi, 1
    mov rsi, msg_x
    mov rdx, 10
    syscall

    mov rax, 0
    mov rdi, 0
    mov rsi, buffer
    mov rdx, 32
    syscall

    call str_to_int
    mov [x], rax

    mov rax, 1
    mov rdi, 1
    mov rsi, msg_y
    mov rdx, 10
    syscall

    mov rax, 0
    mov rdi, 0
    mov rsi, buffer
    mov rdx, 32
    syscall

    call str_to_int
    mov [y], rax

    mov rax, [x]
    mov rbx, [y]
    mov [x], rbx
    mov [y], rax

    mov rax, 1
    mov rdi, 1
    mov rsi, msg_rx
    mov rdx, 8
    syscall

    mov rax, [x]
    call int_to_str

    mov rax, 1
    mov rdi, 1
    mov rsi, newline
    mov rdx, 1
    syscall

    mov rax, 1
    mov rdi, 1
    mov rsi, msg_ry
    mov rdx, 8
    syscall

    mov rax, [y]
    call int_to_str

    mov rax, 1
    mov rdi, 1
    mov rsi, newline
    mov rdx, 1
    syscall

    mov rax, 60
    xor rdi, rdi
    syscall

str_to_int:
    xor rax, rax
    xor rcx, rcx

.loop:
    mov bl, [buffer + rcx]
    cmp bl, 10
    je .fim

    sub bl, '0'
    imul rax, rax, 10
    add rax, rbx

    inc rcx
    jmp .loop

.fim:
    ret

int_to_str:
    mov rcx, 0
    mov rbx, 10

.conv:
    xor rdx, rdx
    div rbx
    add rdx, '0'
    push rdx
    inc rcx
    test rax, rax
    jnz .conv

.print:
    pop rax
    mov [buffer], al

    mov rax, 1
    mov rdi, 1
    mov rsi, buffer
    mov rdx, 1
    syscall

    loop .print
    ret
```

# Exercício 3:

```
section .data
    texto db "digite a string", 0
    newline db 10

section .text
    global _start

_start:

    mov byte [texto], 'X'
    mov byte [texto+1], 'Y'
    mov byte [texto+2], 'Z'

    mov rax, 1
    mov rdi, 1
    mov rsi, texto
    mov rdx, 18
    syscall

    mov rax, 1
    mov rdi, 1
    mov rsi, newline
    mov rdx, 1
    syscall

    mov rax, 60
    xor rdi, rdi
    syscall
```

# Exercício 4:

```
section .data
    msg_x db "Digite x: ", 0
    msg_y db "Digite y: ", 0
    msg_res db "Resultado: ", 0
    newline db 10

section .bss
    x resq 1
    y resq 1
    buffer resb 32

section .text
    global _start

_start:

    mov rax, 1
    mov rdi, 1
    mov rsi, msg_x
    mov rdx, 10
    syscall

    mov rax, 0
    mov rdi, 0
    mov rsi, buffer
    mov rdx, 32
    syscall

    call str_to_int
    mov [x], rax

    mov rax, 1
    mov rdi, 1
    mov rsi, msg_y
    mov rdx, 10
    syscall

    mov rax, 0
    mov rdi, 0
    mov rsi, buffer
    mov rdx, 32
    syscall

    call str_to_int
    mov [y], rax

    mov rax, 1
    mov rcx, [y]
    mov rbx, [x]

.loop:
    cmp rcx, 0
    je .fim
    imul rax, rbx
    dec rcx
    jmp .loop

.fim:

    mov rsi, msg_res
    mov rdx, 11
    mov rax, 1
    mov rdi, 1
    syscall

    call int_to_str

    mov rax, 1
    mov rdi, 1
    mov rsi, newline
    mov rdx, 1
    syscall

    mov rax, 60
    xor rdi, rdi
    syscall

str_to_int:
    xor rax, rax
    xor rcx, rcx

.loop2:
    mov bl, [buffer + rcx]
    cmp bl, 10
    je .fim2

    sub bl, '0'
    imul rax, rax, 10
    add rax, rbx

    inc rcx
    jmp .loop2

.fim2:
    ret

int_to_str:
    mov rcx, 0
    mov rbx, 10

.conv:
    xor rdx, rdx
    div rbx
    add rdx, '0'
    push rdx
    inc rcx
    test rax, rax
    jnz .conv

.print:
    pop rax
    mov [buffer], al

    mov rax, 1
    mov rdi, 1
    mov rsi, buffer
    mov rdx, 1
    syscall

    loop .print
    ret
```

# Exercício 5:
```
section .data
    msg_x db "Digite x: ", 0
    msg_y db "Digite y: ", 0
    msg_res db "Resultado: ", 0
    newline db 10

section .bss
    x resq 1
    y resq 1
    buffer resb 32

section .text
    global _start

_start:

    mov rax, 1
    mov rdi, 1
    mov rsi, msg_x
    mov rdx, 10
    syscall

    mov rax, 0
    mov rdi, 0
    mov rsi, buffer
    mov rdx, 32
    syscall

    call str_to_int
    mov [x], rax
    
    mov rax, 1
    mov rdi, 1
    mov rsi, msg_y
    mov rdx, 10
    syscall

    mov rax, 0
    mov rdi, 0
    mov rsi, buffer
    mov rdx, 32
    syscall

    call str_to_int
    mov [y], rax

    mov rax, [x]
    mov rcx, [y]

.loop:
    cmp rcx, 0
    je .fim
    shl rax, 1
    dec rcx
    jmp .loop

.fim:

    mov rsi, msg_res
    mov rdx, 11
    mov rax, 1
    mov rdi, 1
    syscall

    call int_to_str

    mov rax, 1
    mov rdi, 1
    mov rsi, newline
    mov rdx, 1
    syscall

    mov rax, 60
    xor rdi, rdi
    syscall

str_to_int:
    xor rax, rax
    xor rcx, rcx

.loop2:
    mov bl, [buffer + rcx]
    cmp bl, 10
    je .fim2

    sub bl, '0'
    imul rax, rax, 10
    add rax, rbx

    inc rcx
    jmp .loop2

.fim2:
    ret

int_to_str:
    mov rcx, 0
    mov rbx, 10

.conv:
    xor rdx, rdx
    div rbx
    add rdx, '0'
    push rdx
    inc rcx
    test rax, rax
    jnz .conv

.print:
    pop rax
    mov [buffer], al

    mov rax, 1
    mov rdi, 1
    mov rsi, buffer
    mov rdx, 1
    syscall

    loop .print
    ret
```
