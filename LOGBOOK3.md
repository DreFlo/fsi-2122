# Trabalho realizado na Semana #3

## Identificação

- CVE-2010-2568
- Windows Shell vulnerability that allows attackers to execute arbitrary code.
- Code is executed via a crafted shortcut file, which is not properly handled during icon display in Windows Explorer.
- Affects Windows XP SP3, Server 2003 SP2, Vista SP1 and SP2, Server 2008 SP2 and R2, and Windows 7.

## Catalogação

- VirusBlockAda reported vulnerabilaty on June 17 2010.
- Microsoft released the first patch ion 2 August 2010.
- There is complete loss of system protection and total compromise of system integrity.

## Exploit

- The system is vulnerable when processing a crafted LNK or PIF file.
- This allows the execution of arbitrary code, leading to complete system vulnerabilaty.
- There are currently two verified exploits, one local and one remote, as a way to explore this vulnerabilaty.

## Ataques

- This and 3 other zero-day exploits were used in the infamous Stuxnet worm.
- This vulnerablity was used to spread the worm through infected USB flash drives belonging to companies connected to nuclear program.
- The Stuxnet worm targeted centrifuges crippling Iran's urainum enrichment capabilities.
- Was the first virus that caused physical damage.
