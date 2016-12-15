---
title: "Resoluci&#243;n enlazada tempranamente; pueden producirse errores en tiempo de ejecuci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc42017"
  - "BC42017"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42017"
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Resoluci&#243;n enlazada tempranamente; pueden producirse errores en tiempo de ejecuci&#243;n
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Se asigna un objeto a una variable declarada para ser del [Object \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Cuando declare una variable como `Object`, el compilador debe realizar *enlace en tiempo de ejecución*, que produce operaciones adicionales en tiempo de ejecución.  También se expone la aplicación a posibles errores en tiempo de ejecución.  Por ejemplo, si asigna un <xref:System.Windows.Forms.Form> a la variable `Object` y luego intenta obtener acceso a la propiedad <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName>, el tiempo de ejecución produce una excepción <xref:System.MemberAccessException> porque la clase <xref:System.Windows.Forms.Form> no expone una propiedad `NameTable`.  
  
 Si declara la variable para ser de un tipo específico, el compilador puede realizar en tiempo de compilación el *enlace en tiempo de compilación*.  Así se consigue una mejora de rendimiento, acceso controlado a los miembros del tipo específico y mejor legibilidad de su código.  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratarlas como errores, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC42017  
  
### Para corregir este error  
  
-   Si es posible, declare la variable para que sea de un tipo específico.  
  
## Vea también  
 [Enlace en tiempo de compilación y en tiempo de ejecución](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [Declaración de variables de objeto](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)