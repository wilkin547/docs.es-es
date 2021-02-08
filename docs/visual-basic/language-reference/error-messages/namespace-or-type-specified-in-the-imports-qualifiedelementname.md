---
description: "Más información acerca de: BC40056: el espacio de nombres o tipo especificado en las importaciones ' <qualifiedelementname> ' no contiene ningún miembro público o no se encuentra"
title: El espacio de nombres o tipo especificado en las importaciones '<qualifiedelementname>' no contiene miembros públicos o no se encuentra
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: e98ba70660823196e763300cd33ec1ba9a9db3b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795708"
---
# <a name="bc40056-namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>BC40056: el espacio de nombres o tipo especificado en las importaciones ' \<qualifiedelementname> ' no contiene ningún miembro público o no se encuentra

El espacio de nombres o tipo especificado en las importaciones ' \<qualifiedelementname> ' no contiene ningún miembro público o no se encuentra. Asegúrese de que el espacio de nombres o el tipo estén definidos y que contenga al menos un miembro público. Asegúrese de que el nombre de alias no contenga otros alias.

Una `Imports` instrucción especifica un elemento contenedor que no se puede encontrar o no define ningún `Public` miembro.

Un *elemento contenedor* puede ser un espacio de nombres, una clase, una estructura, un módulo, una interfaz o una enumeración. El elemento contenedor contiene miembros, como variables, procedimientos u otros elementos contenedores.

El propósito de la importación es permitir que el código tenga acceso a los miembros de espacio de nombres o de tipo sin tener que calificarlos. Es posible que el proyecto también tenga que agregar una referencia al espacio de nombres o al tipo. Para obtener más información, vea "importar elementos contenedores" en [referencias a elementos declarados](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

Si el compilador no encuentra el elemento contenedor especificado, no puede resolver las referencias que lo usan. Si encuentra el elemento pero el elemento no expone ningún `Public` miembro, no se puede realizar ninguna referencia correctamente. En cualquier caso, no tiene sentido importar el elemento.

Tenga en cuenta que si importa un elemento contenedor y le asigna un alias de importación, no puede usar ese alias de importación para importar otro elemento. El código siguiente genera un error del compilador.

```vb
Imports winfrm = System.Windows.Forms

' The following statement is INVALID  because it reuses an import alias.

Imports behave = winfrm.Design.Behavior`
```

**Identificador de error:** BC40056

## <a name="to-correct-this-error"></a>Para corregir este error

1. Compruebe que el elemento contenedor es accesible desde el proyecto.

2. Compruebe que la especificación del elemento contenedor no incluye ningún alias de importación de otra importación.

3. Compruebe que el elemento contenedor expone al menos un `Public` miembro.

## <a name="see-also"></a>Vea también

- [Instrucción Imports (Tipo y espacio de nombres de .NET)](../statements/imports-statement-net-namespace-and-type.md)
- [Namespace (Instrucción)](../statements/namespace-statement.md)
- [Público](../modifiers/public.md)
- [Espacios de nombres en Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
