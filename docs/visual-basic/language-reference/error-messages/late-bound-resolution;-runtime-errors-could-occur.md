---
title: Resolución enlazada tempranamente; pueden producirse errores en tiempo de ejecución
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: ef0fa295cadaaa0550be4809ec97c6da13b5e2db
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160436"
---
# <a name="bc42017-late-bound-resolution-runtime-errors-could-occur"></a>BC42017: resolución enlazada en tiempo de ejecución; se pueden producir errores en tiempo de ejecución

Un objeto se asigna a una variable declarada como del [tipo de datos del objeto](../data-types/object-data-type.md).

 Cuando se declara una variable como `Object` , el compilador debe realizar el *enlace*en tiempo de ejecución, lo que produce operaciones adicionales en tiempo de ejecución. También expone la aplicación a posibles errores en tiempo de ejecución. Por ejemplo, si asigna un <xref:System.Windows.Forms.Form> a la `Object` variable e intenta tener acceso a la <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> propiedad, el tiempo de ejecución produce una excepción <xref:System.MemberAccessException> porque la <xref:System.Windows.Forms.Form> clase no expone una `NameTable` propiedad.

 Si declara que la variable es de un tipo específico, el compilador puede realizar el *enlace anticipado* en tiempo de compilación. Esto da como resultado un rendimiento mejorado, el acceso controlado a los miembros del tipo específico y una mejor legibilidad del código.

 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identificador de error:** BC42017

## <a name="to-correct-this-error"></a>Para corregir este error

- Si es posible, declare la variable para que sea de un tipo específico.

## <a name="see-also"></a>Vea también

- [Enlace en tiempo de compilación y en tiempo de ejecución](../../programming-guide/language-features/early-late-binding/index.md)
- [Declaración de variables de objeto](../../programming-guide/language-features/variables/object-variable-declaration.md)
