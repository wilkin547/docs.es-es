---
description: "Más información sobre: BC42107: la propiedad ' <propertyname> ' no devuelve un valor en todas las rutas de código"
title: La propiedad '<propertyname>' no devuelve un valor en todas las rutas de acceso a código
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 9aa0d6fea1feeaf7503f5f8831fbd3de910a4822
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774894"
---
# <a name="bc42107-property-propertyname-doesnt-return-a-value-on-all-code-paths"></a>BC42107: la propiedad ' \<propertyname> ' no devuelve un valor en todas las rutas de código

La propiedad ' \<propertyname> ' no devuelve un valor en todas las rutas de acceso de código. Podría producirse una excepción de referencia nula en tiempo de ejecución al usar el resultado.

Un procedimiento de propiedad `Get` tiene al menos una ruta de acceso posible a través de su código que no devuelve un valor.

 Puede devolver un valor de un procedimiento de propiedad `Get` de cualquiera de las maneras siguientes:

- Asigne el valor al nombre de la propiedad y, a continuación, realice una `Exit Property` instrucción.

- Asigne el valor al nombre de la propiedad y, a continuación, realice la `End Get` instrucción.

- Incluya el valor en una [instrucción return](../statements/return-statement.md).

Si el control pasa a `Exit Property` o `End Get` y no ha asignado ningún valor al nombre de la propiedad, el `Get` procedimiento devuelve el valor predeterminado del tipo de datos de la propiedad. Para obtener más información, vea el tema sobre el comportamiento en la [instrucción function](../statements/function-statement.md).

De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

**Identificador de error:** BC42107

## <a name="to-correct-this-error"></a>Para corregir este error

- Compruebe la lógica del flujo de control y asegúrese de asignar un valor antes de cada instrucción que produce una devolución.

  Es más fácil garantizar que todas las devoluciones del procedimiento devuelvan un valor si siempre se usa la `Return` instrucción. Si lo hace, la última instrucción antes de `End Get` debe ser una `Return` instrucción.

## <a name="see-also"></a>Vea también

- [Procedimientos de propiedad](../../programming-guide/language-features/procedures/property-procedures.md)
- [Property Statement](../statements/property-statement.md)
- [Get (Instrucción)](../statements/get-statement.md)
