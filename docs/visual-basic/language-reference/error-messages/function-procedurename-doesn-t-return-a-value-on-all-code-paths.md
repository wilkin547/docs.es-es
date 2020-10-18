---
title: La función '<procedurename>' no devuelve un valor en todas las rutas de acceso a código
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 19b305e337767dfb34718aed7b665f142851bd36
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163368"
---
# <a name="bc42105-function-procedurename-doesnt-return-a-value-on-all-code-paths"></a>BC42105: la función ' \<procedurename> ' no devuelve un valor en todas las rutas de código

La función ' \<procedurename> ' no devuelve un valor en todas las rutas de acceso de código. ¿Falta una instrucción ' Return '?

 Un `Function` procedimiento tiene al menos una ruta de acceso posible a través de su código que no devuelve un valor.

 Puede devolver un valor de un `Function` procedimiento de cualquiera de las maneras siguientes:

- Incluya el valor en una [instrucción return](../statements/return-statement.md).

- Asigne el valor al `Function` nombre del procedimiento y, a continuación, realice una `Exit Function` instrucción.

- Asigne el valor al `Function` nombre del procedimiento y, a continuación, realice la `End Function` instrucción.

 Si el control pasa a `Exit Function` o `End Function` y no ha asignado ningún valor al nombre del procedimiento, el procedimiento devuelve el valor predeterminado del tipo de datos devuelto. Para obtener más información, vea el tema sobre el comportamiento en la [instrucción function](../statements/function-statement.md).

 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identificador de error:** BC42105

## <a name="to-correct-this-error"></a>Para corregir este error

- Compruebe la lógica del flujo de control y asegúrese de asignar un valor antes de cada instrucción que produce una devolución.

     Es más fácil garantizar que todas las devoluciones del procedimiento devuelvan un valor si siempre se usa la `Return` instrucción. Si lo hace, la última instrucción antes de `End Function` debe ser una `Return` instrucción.

## <a name="see-also"></a>Vea también

- [Procedimientos de función](../../programming-guide/language-features/procedures/function-procedures.md)
- [Instrucción Function](../statements/function-statement.md)
- [Página Compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
