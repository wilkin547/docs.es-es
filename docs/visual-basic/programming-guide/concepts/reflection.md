---
title: "Reflexión (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b7b94e25d2ca9563cd50f454c94092f18e295863
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="reflection-visual-basic"></a><span data-ttu-id="3ca83-102">Reflexión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ca83-102">Reflection (Visual Basic)</span></span>
<span data-ttu-id="3ca83-103">La reflexión proporciona objetos (de tipo <xref:System.Type>) que describen los ensamblados, módulos y tipos.</span><span class="sxs-lookup"><span data-stu-id="3ca83-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="3ca83-104">Puede usar la reflexión para crear dinámicamente una instancia de un tipo, enlazar el tipo a un objeto existente u obtener el tipo desde un objeto existente e invocar sus métodos, o acceder a sus campos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="3ca83-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="3ca83-105">Si usa atributos en el código, la reflexión le permite acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="3ca83-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="3ca83-106">Para obtener más información, consulte [Attributes](https://msdn.microsoft.com/library/5x6cd29c) (Atributos).</span><span class="sxs-lookup"><span data-stu-id="3ca83-106">For more information, see [Attributes](https://msdn.microsoft.com/library/5x6cd29c).</span></span>  
  
 <span data-ttu-id="3ca83-107">Este es un ejemplo simple de reflexión que usa el método estático `GetType`, heredado por todos los tipos de la clase base `Object`, para obtener el tipo de una variable:</span><span class="sxs-lookup"><span data-stu-id="3ca83-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 <span data-ttu-id="3ca83-108">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ca83-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="3ca83-109">En el ejemplo siguiente se usa la reflexión para obtener el nombre completo del ensamblado cargado.</span><span class="sxs-lookup"><span data-stu-id="3ca83-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 <span data-ttu-id="3ca83-110">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ca83-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a><span data-ttu-id="3ca83-111">Información general de la reflexión</span><span class="sxs-lookup"><span data-stu-id="3ca83-111">Reflection Overview</span></span>  
 <span data-ttu-id="3ca83-112">La reflexión resulta útil en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="3ca83-112">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="3ca83-113">Cuando tenga que acceder a atributos en los metadatos del programa.</span><span class="sxs-lookup"><span data-stu-id="3ca83-113">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="3ca83-114">Para obtener más información, consulte [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md) (Recuperar la información almacenada en atributos).</span><span class="sxs-lookup"><span data-stu-id="3ca83-114">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
-   <span data-ttu-id="3ca83-115">Para examinar y crear instancias de tipos en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3ca83-115">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="3ca83-116">Para generar nuevos tipos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3ca83-116">For building new types at runtime.</span></span> <span data-ttu-id="3ca83-117">Usar clases en <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="3ca83-117">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="3ca83-118">Para llevar a cabo métodos de acceso de enlace en tiempo de ejecución en tipos creados en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3ca83-118">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="3ca83-119">Consulte el tema [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md) (Cargar y usar tipos dinámicamente).</span><span class="sxs-lookup"><span data-stu-id="3ca83-119">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3ca83-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="3ca83-120">Related Sections</span></span>  
 <span data-ttu-id="3ca83-121">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="3ca83-121">For more information:</span></span>  
  
-   [<span data-ttu-id="3ca83-122">Reflexión</span><span class="sxs-lookup"><span data-stu-id="3ca83-122">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
-   <span data-ttu-id="3ca83-123">[Viewing Type Information](../../../framework/reflection-and-codedom/viewing-type-information.md) (Ver información tipos)</span><span class="sxs-lookup"><span data-stu-id="3ca83-123">[Viewing Type Information](../../../framework/reflection-and-codedom/viewing-type-information.md)</span></span>  
  
-   <span data-ttu-id="3ca83-124">[Reflection and Generic Types](../../../framework/reflection-and-codedom/reflection-and-generic-types.md) (Reflexión y tipos genéricos)</span><span class="sxs-lookup"><span data-stu-id="3ca83-124">[Reflection and Generic Types](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)</span></span>  
  
-   <xref:System.Reflection.Emit>  
  
-   <span data-ttu-id="3ca83-125">[Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md) (Recuperar la información almacenada en atributos)</span><span class="sxs-lookup"><span data-stu-id="3ca83-125">[Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca83-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ca83-126">See Also</span></span>  
 [<span data-ttu-id="3ca83-127">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3ca83-127">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)  
 [<span data-ttu-id="3ca83-128">Ensamblados en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3ca83-128">Assemblies in the Common Language Runtime</span></span>](https://msdn.microsoft.com/library/k3677y81)
