---
title: "Trabajar con objetos dinámicos (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 366b563764baaa39849356a782ecee264b2ae94f
ms.lasthandoff: 03/13/2017

---
# <a name="working-with-dynamic-objects-visual-basic"></a>Trabajar con objetos dinámicos (Visual Basic)
Objetos dinámicos proporcionan otro mecanismo, distinto de la `Object` tipo en tiempo de ejecución y enlazarlo a un objeto en tiempo de ejecución. Un objeto dinámico expone miembros, como propiedades y métodos en tiempo de ejecución usando interfaces dinámicas que se definen en el <xref:System.Dynamic>espacio de nombres.</xref:System.Dynamic> Puede utilizar las clases en el <xref:System.Dynamic>espacio de nombres para crear objetos que trabajar con estructuras de datos que no coinciden con un tipo o formato estático.</xref:System.Dynamic> También puede utilizar los objetos dinámicos que se definen en lenguajes dinámicos, como IronPython e IronRuby. Para obtener ejemplos que muestran cómo crear objetos dinámicos o utilizar un objeto dinámico definido en un lenguaje dinámico, vea [Tutorial: crear y utilizar objetos dinámicos](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, o <xref:System.Dynamic.ExpandoObject>.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]se enlaza a los objetos en el tiempo de ejecución de lenguaje dinámico y lenguajes dinámicos, como IronPython e IronRuby mediante el <xref:System.Dynamic.IDynamicMetaObjectProvider>interfaz.</xref:System.Dynamic.IDynamicMetaObjectProvider> Ejemplos de clases que implementan la `IDynamicMetaObjectProvider` interfaz son la <xref:System.Dynamic.DynamicObject>y <xref:System.Dynamic.ExpandoObject>clases.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject>  
  
 Si se realiza una llamada de tiempo de ejecución a un objeto que implementa el `IDynamicMetaObjectProvider` interfaz, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enlaza al objeto dinámico mediante esa interfaz. Si se realiza una llamada en tiempo de ejecución a un objeto que no implementa la `IDynamicMetaObjectProvider` interfaz, o si la llamada a la `IDynamicMetaObjectProvider` falla, la interfaz [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enlaza al objeto mediante las capacidades de enlace de la [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Dynamic.DynamicObject></xref:System.Dynamic.DynamicObject>   
 <xref:System.Dynamic.ExpandoObject></xref:System.Dynamic.ExpandoObject>   
 [Tutorial: Crear y utilizar objetos dinámicos](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)   
 [Enlace en tiempo de compilación y en tiempo de ejecución](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
