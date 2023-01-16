; ZAD1-KV2
; Napišite program koji će upaliti LED2 port
; kao bitwise XOR funkciju
; sklopki SW2 i BTN tipkala.

ADDRESS 000
START:	INPUT S0, SW2_PORT
        INPUT S1, BTN_PORT
        XOR S0, S1
        OUTPUT S0, LED2_PORT
        JUMP START

; ZAD2-KV2
; Napišite program koji će na LED1 pokazniku
; prikazati umnožak brojeva SW1*SW2.
; Program rješite pomoću operacija pomicanja.

ADDRESS 000
START:	INPUT S0, SW1_PORT
        INPUT S1, SW2_PORT
        COMPARE S1, 00
        JUMP Z, ISPIS
LOOP:		SL0 S0
        SUB S1, 01
        JUMP NZ, PETLJA
ISPIS:	OUTPUT S0, LED1_PORT
        JUMP START

; ZAD3-KV2
; Primjenom naredbi ADD i ADDCY rješite
; 16-bitno zbrajanje SW1+SW2. Ispišite
; rezultat na HEX1 i HEX2 pokaznicima.

ADDRESS 000
START:	INPUT S0, SW1_PORT
        INPUT S1, SW2_PORT
        LOAD S2, 00
        ADD S0, S1
        ADDCY S2, 00
        OUTPUT S2, HEX1_PORT
        OUTPUT S0, HEX2_PORT
        JUMP START

; ZAD4-KV2
; Primjenom naredbi ADD i ADDCY rješite
; 16-bitno množenje SW1*SW2. Ispišite
; rezultat na HEX1 i HEX2 pokaznicima.

ADDRESS 000
START:	INPUT S0, SW1_PORT
        INPUT S1, SW2_PORT
        LOAD S3, 00 ; FLAG
        COMPARE S1, 00
        JUMP Z, ISPIS
        LOAD S2, 00 ; COUNTER
MNOZI:	ADD S2, 01
        ADD S0, S1
        ADDCY S3, 00
        COMPARE S2, S1
        JUMP NZ, MNOZI
ISPIS:	OUTPUT S3, HEX1_FLAG
        OUTPUT S0, HEX2_FLAG
        JUMP START

; ZAD5-KV2
; Primjenom naredbi SUV i SUBCY rješite
; 16-bitno dijeljenje SW1/SW2. Ispišite
; rezultat na HEX1 i HEX2 pokaznicima
; te ostatak na HE3 i HEX4.

ADDRESS 000
START:	INPUT S0, SW1_PORT
		    INPUT S1, SW2_PORT
		    LOAD S2, 00
		    COMPARE S1, 00
        JUMP Z, ISPIS
        LOAD S3, S0
RAZLIKA:	LOAD S2, FF
          SUB S3, S1
          SUBCY S2, 00
          XOR S2, FF
          COMPARE S2, 00
          JUMP NZ, ISPIS
          LOAD S0, S3
          JUMP RAZLIKA
ISPIS:	OUTPUT S0, HEX1_PORT
        OUTPUT S2, HEX2_PORT
        JUMP START
