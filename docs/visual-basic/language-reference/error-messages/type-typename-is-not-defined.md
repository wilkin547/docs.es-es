---
title: No está definido el tipo '<typename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 195e749e29494d438dbd052e8e308250f4cce1ca
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161899"
---
# <a name="bc30002-type-typename-is-not-defined"></a>BC30002: el tipo ' \<typename> ' no está definido

La instrucción ha hecho referencia a un tipo que no se ha definido. Puede definir un tipo en una instrucción de declaración como `Enum` , `Structure` , `Class` o `Interface` .

 **Identificador de error:** BC30002

## <a name="to-correct-this-error"></a>Para corregir este error

- Asegúrese de que la definición de tipo y su referencia usan la misma ortografía.

- Asegúrese de que la definición de tipo es accesible para la referencia. Por ejemplo, si el tipo está en otro módulo y se ha declarado `Private` , mueva la definición de tipo al módulo que hace la referencia o declárela `Public` .

- Asegúrese de que el espacio de nombres del tipo no se ha redefinido en el proyecto. Si es así, use la `Global` palabra clave para completar el nombre del tipo. Por ejemplo, si un proyecto define un espacio de nombres denominado `System` , <xref:System.Object?displayProperty=nameWithType> no se puede tener acceso al tipo a menos que esté completo con la `Global` palabra clave: `Global.System.Object` .

- Si se define el tipo, pero la biblioteca de objetos o la biblioteca de tipos en la que se define no está registrada en Visual Basic, haga clic en **Agregar referencia** en el menú **proyecto** y, a continuación, seleccione la biblioteca de objetos o la biblioteca de tipos adecuada.

- Asegúrese de que el tipo está en un ensamblado que forma parte del perfil de .NET Framework de destino. Para obtener más información, consulte [Solucionar problemas de versión de .NET Framework de destino](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).

## <a name="see-also"></a>Vea también

- [Espacios de nombres en Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [Instrucción Enum](../statements/enum-statement.md)
- [Structure (Instrucción)](../statements/structure-statement.md)
- [Instrucción Class](../statements/class-statement.md)
- [Instrucción Interface](../statements/interface-statement.md)
- [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)
