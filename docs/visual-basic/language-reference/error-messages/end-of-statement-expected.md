---
description: 'Más información acerca de: BC30205: final de la instrucción esperada'
title: Se esperaba el fin de instrucción
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: a3f309a4674f6de34c0be8abfef31e293a10dec5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796553"
---
# <a name="bc30205-end-of-statement-expected"></a>BC30205: se esperaba el final de la instrucción

La instrucción se completa sintácticamente, pero un elemento de programación adicional sigue el elemento que completa la instrucción. Se requiere un terminador de línea al final de cada instrucción.

 Un terminador de línea divide los caracteres de un archivo de origen de Visual Basic en líneas. Los ejemplos de terminadores de línea son el carácter de retorno de carro Unicode (&HD), el carácter de avance de línea Unicode (&HA) y el carácter de retorno de carro Unicode seguido del carácter de avance de línea Unicode. Para obtener más información sobre los terminadores de línea, vea la [especificación del lenguaje Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).

 **Identificador de error:** BC30205

## <a name="to-correct-this-error"></a>Para corregir este error

1. Compruebe si dos instrucciones diferentes se han colocado involuntariamente en la misma línea.

2. Inserte un terminador de línea después del elemento que completa la instrucción.

## <a name="see-also"></a>Vea también

- [Procedimiento Interrupción y combinación de instrucciones en código](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Instrucciones](../../programming-guide/language-features/statements.md)
