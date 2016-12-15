---
title: "Trabajar con objetos din&#225;micos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "objetos dinámicos [Visual Basic]"
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Trabajar con objetos din&#225;micos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Los objetos dinámicos proporcionan otro mecanismo, distinto al del tipo `Object`, para enlazar un objeto en tiempo de ejecución.  Un objeto dinámico expone miembros, como propiedades y métodos, en tiempo de ejecución usando interfaces dinámicas que se definen en el espacio de nombres <xref:System.Dynamic>.  Puede usar las clases del espacio de nombres <xref:System.Dynamic> para crear objetos que funcionen con estructuras de datos que no se ajusten un formato o tipo estático.  También puede usar los objetos dinámicos que se definen en lenguajes dinámicos, como IronPython e IronRuby.  Para obtener ejemplos en los que se muestra cómo se crean objetos dinámicos o se usa un objeto dinámico definido en un lenguaje dinámico, vea [Tutorial: Crear y utilizar objetos dinámicos](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>o <xref:System.Dynamic.ExpandoObject>.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] se enlaza a objetos de tiempo de ejecución de lenguajes dinámicos y lenguajes dinámicos, como IronPython e IronRuby, mediante la interfaz <xref:System.Dynamic.IDynamicMetaObjectProvider>.  Algunos ejemplos de clases que implementan la interfaz `IDynamicMetaObjectProvider` son las clases <xref:System.Dynamic.DynamicObject> y <xref:System.Dynamic.ExpandoObject>.  
  
 Si se realiza una llamada enlazada en tiempo de ejecución a un objeto que implementa la interfaz `IDynamicMetaObjectProvider`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enlaza al objeto dinámico mediante esa interfaz.  Si se realiza una llamada enlazada en tiempo de ejecución a un objeto que no implementa la interfaz `IDynamicMetaObjectProvider`, o si se produce un error en la llamada a la interfaz `IDynamicMetaObjectProvider`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enlaza al objeto mediante las capacidades de enlace en tiempo de ejecución del runtime de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## Vea también  
 <xref:System.Dynamic.DynamicObject>   
 <xref:System.Dynamic.ExpandoObject>   
 [Tutorial: Crear y utilizar objetos dinámicos](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)   
 [Enlace en tiempo de compilación y en tiempo de ejecución](../../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)