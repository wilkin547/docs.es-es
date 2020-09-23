---
title: Trabajo con objetos dinámicos
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 45f8b5c327d40f93b59c2115c75b3b7d385f5a8d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91057928"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Trabajar con objetos dinámicos (Visual Basic)

Los objetos dinámicos proporcionan otra forma, excepto el `Object` tipo, para enlazar en tiempo de ejecución a un objeto en tiempo de ejecución. Un objeto dinámico expone miembros como propiedades y métodos en tiempo de ejecución mediante interfaces dinámicas que se definen en el <xref:System.Dynamic> espacio de nombres. Puede utilizar las clases del espacio de <xref:System.Dynamic> nombres para crear objetos que funcionen con estructuras de datos que no coincidan con un tipo o formato estático. También puede usar los objetos dinámicos que se definen en lenguajes dinámicos como IronPython e IronRuby. Para obtener ejemplos que muestran cómo crear objetos dinámicos o usar un objeto dinámico definido en un lenguaje dinámico, vea [Tutorial: crear y usar objetos dinámicos](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject> o <xref:System.Dynamic.ExpandoObject> .  
  
 Visual Basic enlaza a objetos de Dynamic Language Runtime y lenguajes dinámicos como IronPython e IronRuby mediante la <xref:System.Dynamic.IDynamicMetaObjectProvider> interfaz. Ejemplos de clases que implementan la `IDynamicMetaObjectProvider` interfaz son <xref:System.Dynamic.DynamicObject> las <xref:System.Dynamic.ExpandoObject> clases y.  
  
 Si se realiza una llamada enlazada en tiempo de ejecución a un objeto que implementa la `IDynamicMetaObjectProvider` interfaz, Visual Basic enlaza al objeto dinámico usando esa interfaz. Si se realiza una llamada enlazada en tiempo de ejecución a un objeto que no implementa la `IDynamicMetaObjectProvider` interfaz, o si se produce un error en la llamada a la `IDynamicMetaObjectProvider` interfaz, Visual Basic enlaza al objeto utilizando las capacidades de enlace en tiempo de ejecución del Visual Basic Runtime.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [Tutorial: Crear y usar objetos dinámicos](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [Enlace en tiempo de compilación y en tiempo de ejecución](index.md)
