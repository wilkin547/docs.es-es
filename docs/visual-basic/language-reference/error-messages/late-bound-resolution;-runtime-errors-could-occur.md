---
title: "Resolución enlazada tempranamente; pueden producirse errores en tiempo de ejecución"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8d01164914b484ef689654f048a8743f3c2eb669
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a>Resolución enlazada tempranamente; pueden producirse errores en tiempo de ejecución
Un objeto se asigna a una variable que se declara de la [tipo de datos de objeto](../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Cuando se declara una variable como `Object`, el compilador debe realizar *enlace más tarde*, que produce operaciones adicionales en tiempo de ejecución. También expone la aplicación a posibles errores en tiempo de ejecución. Por ejemplo, si asigna un <xref:System.Windows.Forms.Form> a la `Object` variable y, a continuación, intente obtener acceso a la <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> propiedad, el runtime produce una <xref:System.MemberAccessException> porque el <xref:System.Windows.Forms.Form> clase no expone un `NameTable` propiedad.  
  
 Si se declara la variable para que sea de un tipo específico, el compilador puede realizar *el enlace anticipado* en tiempo de compilación. Esto da como resultado un mejor rendimiento, acceso controlado a los miembros del tipo específico y mejorar la legibilidad del código.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC42017  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si es posible, declare la variable de un tipo específico.  
  
## <a name="see-also"></a>Vea también  
 [Enlace en tiempo de compilación y en tiempo de ejecución](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [Declaración de variables de objeto](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
