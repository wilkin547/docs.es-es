---
title: Trabajar con objetos dinámicos
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 20d007fb48e1db352bab6d8e25d2e60e02554732
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345174"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Trabajar con objetos dinámicos (Visual Basic)
Los objetos dinámicos proporcionan otra forma, excepto el tipo `Object`, para enlazar en tiempo de ejecución a un objeto en tiempo de ejecución. Un objeto dinámico expone miembros como propiedades y métodos en tiempo de ejecución mediante interfaces dinámicas que se definen en el espacio de nombres <xref:System.Dynamic>. Puede utilizar las clases del espacio de nombres <xref:System.Dynamic> para crear objetos que funcionen con estructuras de datos que no coincidan con un tipo o formato estático. También puede usar los objetos dinámicos que se definen en lenguajes dinámicos como IronPython e IronRuby. Para obtener ejemplos que muestran cómo crear objetos dinámicos o usar un objeto dinámico definido en un lenguaje dinámico, vea [Tutorial: crear y usar objetos dinámicos](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>o <xref:System.Dynamic.ExpandoObject>.  
  
 Visual Basic enlaza a objetos de Dynamic Language Runtime y lenguajes dinámicos como IronPython e IronRuby mediante la interfaz <xref:System.Dynamic.IDynamicMetaObjectProvider>. Ejemplos de clases que implementan la interfaz `IDynamicMetaObjectProvider` son las clases <xref:System.Dynamic.DynamicObject> y <xref:System.Dynamic.ExpandoObject>.  
  
 Si se realiza una llamada enlazada en tiempo de ejecución a un objeto que implementa la interfaz de `IDynamicMetaObjectProvider`, Visual Basic enlaza al objeto dinámico usando esa interfaz. Si se realiza una llamada enlazada en tiempo de ejecución a un objeto que no implementa la interfaz `IDynamicMetaObjectProvider`, o si se produce un error en la llamada a la interfaz `IDynamicMetaObjectProvider`, Visual Basic enlaza al objeto utilizando las capacidades de enlace en tiempo de ejecución del Visual Basic Runtime.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) (Tutorial: Crear y usar objetos dinámicos [C# y Visual Basic])
- [Enlace en tiempo de compilación y en tiempo de ejecución](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
