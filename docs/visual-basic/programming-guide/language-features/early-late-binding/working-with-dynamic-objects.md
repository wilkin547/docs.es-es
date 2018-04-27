---
title: Trabajar con objetos dinámicos (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f00c57107da5e6ea428e14964d8fa4a870bc96c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="684f6-102">Trabajar con objetos dinámicos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="684f6-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="684f6-103">Objetos dinámicos proporcionan otro mecanismo, excepto el `Object` tipo en tiempo de ejecución y enlazarlo a un objeto en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="684f6-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="684f6-104">Un objeto dinámico expone miembros, como propiedades y métodos en tiempo de ejecución usando interfaces dinámicas que se definen en el <xref:System.Dynamic> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="684f6-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="684f6-105">Puede utilizar las clases en el <xref:System.Dynamic> espacio de nombres para crear objetos que trabajar con estructuras de datos que no coincide con un tipo o formato estático.</span><span class="sxs-lookup"><span data-stu-id="684f6-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="684f6-106">También puede usar los objetos dinámicos que se definen en lenguajes dinámicos, como IronPython e IronRuby.</span><span class="sxs-lookup"><span data-stu-id="684f6-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="684f6-107">Para obtener ejemplos que muestran cómo crear objetos dinámicos o utilizar un objeto dinámico definido en un lenguaje dinámico, vea [Tutorial: crear y utilizar objetos dinámicos](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, o <xref:System.Dynamic.ExpandoObject>.</span><span class="sxs-lookup"><span data-stu-id="684f6-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 <span data-ttu-id="684f6-108">Visual Basic se enlaza a los objetos en el tiempo de ejecución de lenguaje dinámico y lenguajes dinámicos, como IronPython e IronRuby mediante el <xref:System.Dynamic.IDynamicMetaObjectProvider> interfaz.</span><span class="sxs-lookup"><span data-stu-id="684f6-108">Visual Basic binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="684f6-109">Algunos ejemplos de clases que implementan la `IDynamicMetaObjectProvider` interfaz son el <xref:System.Dynamic.DynamicObject> y <xref:System.Dynamic.ExpandoObject> clases.</span><span class="sxs-lookup"><span data-stu-id="684f6-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="684f6-110">Si se realiza una llamada enlazada en tiempo de ejecución de ejecución a un objeto que implementa la `IDynamicMetaObjectProvider` de la interfaz, Visual Basic se enlaza al objeto dinámico mediante esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="684f6-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, Visual Basic binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="684f6-111">Si se realiza una llamada en tiempo de ejecución a un objeto que no implementa la `IDynamicMetaObjectProvider` interfaz, o si la llamada a la `IDynamicMetaObjectProvider` se produce un error en la interfaz, Visual Basic se enlaza al objeto utilizando las capacidades de enlace en tiempo de ejecución de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="684f6-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, Visual Basic binds to the object by using the late-binding capabilities of the Visual Basic runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="684f6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="684f6-112">See Also</span></span>  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 <span data-ttu-id="684f6-113">[Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) (Tutorial: Crear y usar objetos dinámicos [C# y Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="684f6-113">[Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)</span></span>  
 [<span data-ttu-id="684f6-114">Enlace en tiempo de compilación y en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="684f6-114">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
