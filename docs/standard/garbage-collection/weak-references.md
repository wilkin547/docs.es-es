---
title: Referencias parciales
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak references, short
- weak references, using
- weak references, long
- garbage collection, weak references
ms.assetid: 6a600fe5-3af3-4c64-82da-10a0a8e2d79b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 906c23caa7065486bb094ad2475ed9e7e24b3d9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="weak-references"></a><span data-ttu-id="5bd1b-102">Referencias parciales</span><span class="sxs-lookup"><span data-stu-id="5bd1b-102">Weak References</span></span>
<span data-ttu-id="5bd1b-103">El recolector de elementos no utilizados no puede recopilar un objeto que está siendo usado por una aplicación mientras el código de aplicación pueda llegar a ese objeto.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-103">The garbage collector cannot collect an object in use by an application while the application's code can reach that object.</span></span> <span data-ttu-id="5bd1b-104">En este caso, se dice que la aplicación tiene una referencia segura al objeto.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-104">The application is said to have a strong reference to the object.</span></span>  
  
 <span data-ttu-id="5bd1b-105">Una referencia débil permite que el recolector de elementos no utilizados recopile el objeto mientras sigue permitiendo que la aplicación tenga acceso al objeto.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-105">A weak reference permits the garbage collector to collect the object while still allowing the application to access the object.</span></span> <span data-ttu-id="5bd1b-106">Una referencia débil es válida solo durante un período indeterminado de tiempo, hasta que el objeto se recopila cuando no existe ninguna referencia segura.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-106">A weak reference is valid only during the indeterminate amount of time until the object is collected when no strong references exist.</span></span> <span data-ttu-id="5bd1b-107">Cuando se usa una referencia débil, la aplicación todavía puede obtener una referencia segura al objeto, lo que evita que se recopile.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-107">When you use a weak reference, the application can still obtain a strong reference to the object, which prevents it from being collected.</span></span> <span data-ttu-id="5bd1b-108">Pero, siempre existe el riesgo de que el recolector de elementos no utilizados llegue al objeto antes de que se restablezca una referencia segura.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-108">However, there is always the risk that the garbage collector will get to the object first before a strong reference is reestablished.</span></span>  
  
 <span data-ttu-id="5bd1b-109">Las referencias débiles son útiles para objetos que usan mucha memoria, pero que pueden volverse a crear fácilmente si los reclama la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-109">Weak references are useful for objects that use a lot of memory, but can be recreated easily if they are reclaimed by garbage collection.</span></span>  
  
 <span data-ttu-id="5bd1b-110">Imagine que una vista de árbol en una aplicación de formularios Windows Forms muestra una elección jerárquica compleja de opciones al usuario.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-110">Suppose a tree view in a Windows Forms application displays a complex hierarchical choice of options to the user.</span></span> <span data-ttu-id="5bd1b-111">Si la cantidad de datos subyacentes es grande, mantener el árbol en memoria es ineficaz cuando el usuario está ocupado en otra parte de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-111">If the underlying data is large, keeping the tree in memory is inefficient when the user is involved with something else in the application.</span></span>  
  
 <span data-ttu-id="5bd1b-112">Cuando el usuario cambia a otra parte de la aplicación, puede usar el <xref:System.WeakReference> clase para crear una referencia débil al árbol y destruir todas las referencias seguras.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-112">When the user switches away to another part of the application, you can use the <xref:System.WeakReference> class to create a weak reference to the tree and destroy all strong references.</span></span> <span data-ttu-id="5bd1b-113">Cuando el usuario vuelve al árbol, la aplicación intenta obtener una referencia segura al árbol y, si la obtiene, evita tener que reconstruir el árbol.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-113">When the user switches back to the tree, the application attempts to obtain a strong reference to the tree and, if successful, avoids reconstructing the tree.</span></span>  
  
 <span data-ttu-id="5bd1b-114">Para establecer una referencia débil a un objeto, se crea un <xref:System.WeakReference> utilizando la instancia del objeto para realizar su seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-114">To establish a weak reference with an object, you create a <xref:System.WeakReference> using the instance of the object to be tracked.</span></span> <span data-ttu-id="5bd1b-115">A continuación, establezca el <xref:System.WeakReference.Target%2A> propiedad en ese objeto y el conjunto original hacen referencia al objeto para `null`.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-115">You then set the <xref:System.WeakReference.Target%2A> property to that object and set the original reference to the object to `null`.</span></span> <span data-ttu-id="5bd1b-116">Para obtener un ejemplo de código, consulte <xref:System.WeakReference> en la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-116">For a code example, see <xref:System.WeakReference> in the class library.</span></span>  
  
## <a name="short-and-long-weak-references"></a><span data-ttu-id="5bd1b-117">Referencias débiles cortas y largas</span><span class="sxs-lookup"><span data-stu-id="5bd1b-117">Short and Long Weak References</span></span>  
 <span data-ttu-id="5bd1b-118">Puede crear una referencia débil corta o una referencia débil larga:</span><span class="sxs-lookup"><span data-stu-id="5bd1b-118">You can create a short weak reference or a long weak reference:</span></span>  
  
-   <span data-ttu-id="5bd1b-119">Short</span><span class="sxs-lookup"><span data-stu-id="5bd1b-119">Short</span></span>  
  
     <span data-ttu-id="5bd1b-120">El destino de una referencia débil corta se convierte en `null` cuando el objeto es reclamado por la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-120">The target of a short weak reference becomes `null` when the object is reclaimed by garbage collection.</span></span> <span data-ttu-id="5bd1b-121">La referencia débil es, en sí, un objeto administrado y está sujeta a la recolección de elementos no utilizados igual que cualquier otro objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-121">The weak reference is itself a managed object, and is subject to garbage collection just like any other managed object.</span></span>  <span data-ttu-id="5bd1b-122">Una referencia débil corta es el constructor predeterminado para <xref:System.WeakReference>.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-122">A short weak reference is the default constructor for <xref:System.WeakReference>.</span></span>  
  
-   <span data-ttu-id="5bd1b-123">Long</span><span class="sxs-lookup"><span data-stu-id="5bd1b-123">Long</span></span>  
  
     <span data-ttu-id="5bd1b-124">Se conserva una referencia débil larga después del objeto <xref:System.Object.Finalize%2A> ha llamado al método.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-124">A long weak reference is retained after the object's <xref:System.Object.Finalize%2A> method has been called.</span></span> <span data-ttu-id="5bd1b-125">Esto permite que el objeto se vuelva a crear, pero el estado del objeto sigue siendo imprevisible.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-125">This allows the object to be recreated, but the state of the object remains unpredictable.</span></span> <span data-ttu-id="5bd1b-126">Para utilizar una referencia larga, especifique `true` en el <xref:System.WeakReference> constructor.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-126">To use a long reference, specify `true` in the <xref:System.WeakReference> constructor.</span></span>  
  
     <span data-ttu-id="5bd1b-127">Si el tipo del objeto no tiene un <xref:System.Object.Finalize%2A> la funcionalidad de la referencia débil corta de método, se aplica y la referencia débil es válida solo hasta que se recopile el destino, lo que puede producirse en cualquier momento después el finalizador se ejecute.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-127">If the object's type does not have a <xref:System.Object.Finalize%2A> method, the short weak reference functionality applies and the weak reference is valid only until the target is collected, which can occur anytime after the finalizer is run.</span></span>  
  
 <span data-ttu-id="5bd1b-128">Para establecer una referencia segura y vuelve a utilizar el objeto, convierte el <xref:System.WeakReference.Target%2A> propiedad de un <xref:System.WeakReference> para el tipo del objeto.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-128">To establish a strong reference and use the object again, cast the <xref:System.WeakReference.Target%2A> property of a <xref:System.WeakReference> to the type of the object.</span></span> <span data-ttu-id="5bd1b-129">Si el <xref:System.WeakReference.Target%2A> propiedad devuelve `null`, el objeto se ha recopilado; en caso contrario, aún puede usar el objeto porque la aplicación ha recuperado una referencia segura a él.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-129">If the <xref:System.WeakReference.Target%2A> property returns `null`, the object was collected; otherwise, you can continue to use the object because the application has regained a strong reference to it.</span></span>  
  
## <a name="guidelines-for-using-weak-references"></a><span data-ttu-id="5bd1b-130">Directrices para usar referencias débiles</span><span class="sxs-lookup"><span data-stu-id="5bd1b-130">Guidelines for Using Weak References</span></span>  
 <span data-ttu-id="5bd1b-131">Use referencias débiles largas solo cuando sea necesario, ya que el estado del objeto es imprevisible después de la finalización.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-131">Use long weak references only when necessary as the state of the object is unpredictable after finalization.</span></span>  
  
 <span data-ttu-id="5bd1b-132">Evite usar referencias débiles a objetos pequeños porque el propio puntero puede ser igual de grande o mayor.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-132">Avoid using weak references to small objects because the pointer itself may be as large or larger.</span></span>  
  
 <span data-ttu-id="5bd1b-133">Evite usar referencias débiles como solución automática para problemas de administración de memoria.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-133">Avoid using weak references as an automatic solution to memory management problems.</span></span> <span data-ttu-id="5bd1b-134">En su lugar, desarrolle una directiva eficaz de almacenamiento en caché para controlar los objetos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5bd1b-134">Instead, develop an effective caching policy for handling your application's objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd1b-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bd1b-135">See Also</span></span>  
 [<span data-ttu-id="5bd1b-136">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="5bd1b-136">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
