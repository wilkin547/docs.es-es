---
title: Trabajar con objetos dinámicos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: ea7d7aae1cd79a0243a9c721b5e3958fba82f84f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832079"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Trabajar con objetos dinámicos (Visual Basic)
Objetos dinámicos proporcionan otra forma, no sea el `Object` tipo, enlazar en tiempo de ejecución a un objeto en tiempo de ejecución. Un objeto dinámico expone miembros como propiedades y métodos en tiempo de ejecución mediante el uso de interfaces dinámicas que se definen en el <xref:System.Dynamic> espacio de nombres. Puede usar las clases en el <xref:System.Dynamic> espacio de nombres para crear objetos que trabajar con estructuras de datos que no coinciden con un formato o tipo estático. También puede usar los objetos dinámicos que se definen en los lenguajes dinámicos como IronPython e IronRuby. Para obtener ejemplos que muestran cómo crear objetos dinámicos o usar un objeto dinámico definido en un lenguaje dinámico, vea [Tutorial: Crear y utilizar objetos dinámicos](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, o <xref:System.Dynamic.ExpandoObject>.  
  
 Visual Basic se enlaza a los objetos desde la dynamic language runtime y los lenguajes dinámicos como IronPython e IronRuby utilizando el <xref:System.Dynamic.IDynamicMetaObjectProvider> interfaz. Ejemplos de clases que implementan la `IDynamicMetaObjectProvider` interfaz son el <xref:System.Dynamic.DynamicObject> y <xref:System.Dynamic.ExpandoObject> clases.  
  
 Si se realiza una llamada enlazada en tiempo de ejecución a un objeto que implementa el `IDynamicMetaObjectProvider` interfaz, Visual Basic se enlaza el objeto dinámico mediante el uso de esa interfaz. Si se realiza una llamada enlazada en tiempo de ejecución a un objeto que no implementa la `IDynamicMetaObjectProvider` interfaz, o si la llamada a la `IDynamicMetaObjectProvider` se produce un error en la interfaz, Visual Basic se enlaza al objeto utilizando las capacidades de enlace en tiempo de ejecución de Visual Basic.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [Tutorial: Crear y usar objetos dinámicos](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [Enlace en tiempo de compilación y en tiempo de ejecución](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
