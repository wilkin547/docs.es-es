---
title: Clase Exception y propiedades
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, Exception class
- Exception class
ms.assetid: e2e1f8c4-e7b4-467d-9a66-13c90861221d
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 253a9846e484aa4e54c3433b0bbc8623519bbb7e
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2017
---
# <a name="exception-class-and-properties"></a><span data-ttu-id="9e3b7-102">Clase Exception y propiedades</span><span class="sxs-lookup"><span data-stu-id="9e3b7-102">Exception class and properties</span></span>

<span data-ttu-id="9e3b7-103">La clase <xref:System.Exception> es la clase base de la que heredan las excepciones.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-103">The <xref:System.Exception> class is the base class from which exceptions inherit.</span></span> <span data-ttu-id="9e3b7-104">Por ejemplo, la jerarquía de clases de <xref:System.InvalidCastException> es como sigue:</span><span class="sxs-lookup"><span data-stu-id="9e3b7-104">For example, the <xref:System.InvalidCastException> class hierarchy is as follows:</span></span>

```
Object
  Exception
    SystemException
       InvalidCastException
```

<span data-ttu-id="9e3b7-105">La clase <xref:System.Exception> tiene las siguientes propiedades que facilitan la comprensión de una excepción.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-105">The <xref:System.Exception> class has the following properties that help make understanding an exception easier.</span></span>

| <span data-ttu-id="9e3b7-106">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="9e3b7-106">Property Name</span></span> | <span data-ttu-id="9e3b7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e3b7-107">Description</span></span> |
| ------------- | ----------- |
| <xref:System.Exception.Data> | <span data-ttu-id="9e3b7-108">Un <xref:System.Collections.IDictionary> que contiene datos arbitrarios en pares de clave y valor.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-108">An <xref:System.Collections.IDictionary> that holds arbitrary data in key-value pairs.</span></span> |
| <xref:System.Exception.HelpLink> | <span data-ttu-id="9e3b7-109">Puede contener una dirección URL (o URN) a un archivo de ayuda que proporciona amplia información sobre la causa de una excepción.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-109">Can hold a URL (or URN) to a help file that provides extensive information about the cause of an exception.</span></span> |
| <xref:System.Exception.InnerException> | <span data-ttu-id="9e3b7-110">Esta propiedad puede usarse para crear y mantener una serie de excepciones durante el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-110">This property can be used to create and preserve a series of exceptions during exception handling.</span></span> <span data-ttu-id="9e3b7-111">Puede usarla para crear una nueva excepción que contiene excepciones detectadas con anterioridad.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-111">You can use it to create a new exception that contains previously caught exceptions.</span></span> <span data-ttu-id="9e3b7-112">La segunda excepción en la propiedad <xref:System.Exception.InnerException> puede capturar la excepción original, lo que permite que el código que controla la segunda excepción examine la información adicional.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-112">The original exception can be captured by the second exception in the <xref:System.Exception.InnerException> property, allowing code that handles the second exception to examine the additional information.</span></span> <span data-ttu-id="9e3b7-113">Por ejemplo, supongamos que tiene un método que recibe un argumento que contiene un formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-113">For example, suppose you have a method that receives an argument that's improperly formatted.</span></span>  <span data-ttu-id="9e3b7-114">El código intenta leer el argumento, pero se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-114">The code tries to read the argument, but an exception is thrown.</span></span> <span data-ttu-id="9e3b7-115">El método detecta la excepción e inicia <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-115">The method catches the exception and throws a <xref:System.FormatException>.</span></span> <span data-ttu-id="9e3b7-116">Para mejorar la capacidad del autor de llamada a la hora de determinar por qué se inicia una excepción, a veces, para un método es recomendable detectar una excepción iniciada por una rutina auxiliar y, después, iniciar una excepción más indicativa del error que se ha producido.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-116">To improve the caller's ability to determine the reason an exception is thrown, it is sometimes desirable for a method to catch an exception thrown by a helper routine and then throw an exception more indicative of the error that has occurred.</span></span> <span data-ttu-id="9e3b7-117">Puede crear una excepción nueva y más significativa, donde se puede establecer la referencia a la excepción interna en la excepción original.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-117">A new and more meaningful exception can be created, where the inner exception reference can be set to the original exception.</span></span> <span data-ttu-id="9e3b7-118">Después, se puede iniciar esta excepción más significativa para el autor de llamada.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-118">This more meaningful exception can then be thrown to the caller.</span></span> <span data-ttu-id="9e3b7-119">Tenga en cuenta que con esta funcionalidad, puede crear una serie de excepciones vinculadas que termina con la excepción que se inicia en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-119">Note that with this functionality, you can create a series of linked exceptions that ends with the exception that was thrown first.</span></span> |
| <xref:System.Exception.Message> | <span data-ttu-id="9e3b7-120">Proporciona detalles sobre la causa de una excepción.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-120">Provides details about the cause of an exception.</span></span>
| <xref:System.Exception.Source> | <span data-ttu-id="9e3b7-121">Devuelve o establece el nombre de la aplicación o del objeto que generó el error.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-121">Gets or sets the name of the application or the object that causes the error.</span></span> |
| <xref:System.Exception.StackTrace>| <span data-ttu-id="9e3b7-122">Contiene un seguimiento de la pila que puede usarse para determinar dónde se produjo un error.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-122">Contains a stack trace that can be used to determine where an error occurred.</span></span> <span data-ttu-id="9e3b7-123">El seguimiento de la pila contiene el nombre del archivo de código fuente y el número de línea del programa si está disponible la información de depuración.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-123">The stack trace includes the source file name and program line number if debugging information is available.</span></span> |

<span data-ttu-id="9e3b7-124">La mayoría de las clases que heredan de <xref:System.Exception> no implementan miembros adicionales ni proporcionan funciones adicionales; simplemente heredan de <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-124">Most of the classes that inherit from <xref:System.Exception> do not implement additional members or provide additional functionality; they simply inherit from <xref:System.Exception>.</span></span> <span data-ttu-id="9e3b7-125">Por tanto, se puede encontrar la información más importante para una excepción en la jerarquía de clases de excepción, el nombre de la excepción y la información contenida en la excepción.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-125">Therefore, the most important information for an exception can be found in the hierarchy of exception classes, the exception name, and the information contained in the exception.</span></span>

<span data-ttu-id="9e3b7-126">Se recomienda que producir y detectar solo los objetos que derivan de <xref:System.Exception>, pero se puede producir cualquier objeto que se deriva de la <xref:System.Object> clase como una excepción.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-126">We recommend that you throw and catch only objects that derive from <xref:System.Exception>, but you can throw any object that derives from the <xref:System.Object> class as an exception.</span></span> <span data-ttu-id="9e3b7-127">Tenga en cuenta que no todos los lenguajes admiten iniciar y detectar objetos que no se derivan de <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="9e3b7-127">Note that not all languages support throwing and catching objects that do not derive from <xref:System.Exception>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9e3b7-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e3b7-128">See Also</span></span>  
[<span data-ttu-id="9e3b7-129">Excepciones</span><span class="sxs-lookup"><span data-stu-id="9e3b7-129">Exceptions</span></span>](index.md)
