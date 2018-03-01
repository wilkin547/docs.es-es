---
title: "Trabajar con objetos dinámicos (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: da70c1e4c7398ad46d48c85b62ab884675bd1a73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Trabajar con objetos dinámicos (Visual Basic)
Objetos dinámicos proporcionan otro mecanismo, excepto el `Object` tipo en tiempo de ejecución y enlazarlo a un objeto en tiempo de ejecución. Un objeto dinámico expone miembros, como propiedades y métodos en tiempo de ejecución usando interfaces dinámicas que se definen en el <xref:System.Dynamic> espacio de nombres. Puede utilizar las clases en el <xref:System.Dynamic> espacio de nombres para crear objetos que trabajar con estructuras de datos que no coincide con un tipo o formato estático. También puede usar los objetos dinámicos que se definen en lenguajes dinámicos, como IronPython e IronRuby. Para obtener ejemplos que muestran cómo crear objetos dinámicos o utilizar un objeto dinámico definido en un lenguaje dinámico, vea [Tutorial: crear y utilizar objetos dinámicos](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, o <xref:System.Dynamic.ExpandoObject>.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]enlaza a los objetos en el tiempo de ejecución de lenguaje dinámico y lenguajes dinámicos, como IronPython e IronRuby mediante el <xref:System.Dynamic.IDynamicMetaObjectProvider> interfaz. Algunos ejemplos de clases que implementan la `IDynamicMetaObjectProvider` interfaz son el <xref:System.Dynamic.DynamicObject> y <xref:System.Dynamic.ExpandoObject> clases.  
  
 Si se realiza una llamada enlazada en tiempo de ejecución de ejecución a un objeto que implementa el `IDynamicMetaObjectProvider` interfaz, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] enlaza al objeto dinámico mediante esa interfaz. Si se realiza una llamada en tiempo de ejecución a un objeto que no implementa la `IDynamicMetaObjectProvider` interfaz, o si la llamada a la `IDynamicMetaObjectProvider` se produce un error, la interfaz [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] enlaza al objeto mediante las capacidades de enlace de la [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) (Tutorial: Crear y usar objetos dinámicos [C# y Visual Basic])  
 [Enlace en tiempo de compilación y en tiempo de ejecución](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
