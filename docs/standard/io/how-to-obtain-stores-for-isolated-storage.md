---
title: "Cómo: Obtener los almacenes de almacenamiento aislado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- stores, obtaining
- storing data using isolated storage, obtaining stores
- isolated storage, obtaining stores
- data stores, obtaining
- data storage using isolated storage, obtaining stores
ms.assetid: fcb6b178-d526-47c4-b029-e946f880f9db
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bb0b877aa0f4cee36bd1f8c1cea624cf9368fbaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-stores-for-isolated-storage"></a><span data-ttu-id="ee160-102">Cómo: Obtener los almacenes de almacenamiento aislado</span><span class="sxs-lookup"><span data-stu-id="ee160-102">How to: Obtain Stores for Isolated Storage</span></span>
<span data-ttu-id="ee160-103">Un almacén aislado expone un sistema de archivos virtual dentro de un compartimiento de datos.</span><span class="sxs-lookup"><span data-stu-id="ee160-103">An isolated store exposes a virtual file system within a data compartment.</span></span> <span data-ttu-id="ee160-104">La <xref:System.IO.IsolatedStorage.IsolatedStorageFile> clase proporciona una serie de métodos para interactuar con un almacén aislado.</span><span class="sxs-lookup"><span data-stu-id="ee160-104">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile> class supplies a number of methods for interacting with an isolated store.</span></span> <span data-ttu-id="ee160-105">Para crear y recuperar almacenes, <xref:System.IO.IsolatedStorage.IsolatedStorageFile> proporciona tres métodos estáticos:</span><span class="sxs-lookup"><span data-stu-id="ee160-105">To create and retrieve stores, <xref:System.IO.IsolatedStorage.IsolatedStorageFile> provides three static methods:</span></span>  
  
-   <span data-ttu-id="ee160-106"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>Devuelve el almacenamiento que está aislado por usuario y ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ee160-106"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> returns storage that is isolated by user and assembly.</span></span>  
  
-   <span data-ttu-id="ee160-107"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>Devuelve el almacenamiento que está aislado por dominio y ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ee160-107"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> returns storage that is isolated by domain and assembly.</span></span>  
  
     <span data-ttu-id="ee160-108">Ambos métodos recuperan un almacén que pertenece al código desde el que se les llama.</span><span class="sxs-lookup"><span data-stu-id="ee160-108">Both methods retrieve a store that belongs to the code from which they are called.</span></span>  
  
-   <span data-ttu-id="ee160-109">El método estático <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> devuelve un almacén aislado que se especifica pasando una combinación de parámetros de ámbito.</span><span class="sxs-lookup"><span data-stu-id="ee160-109">The static method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> returns an isolated store that is specified by passing in a combination of scope parameters.</span></span>  
  
 <span data-ttu-id="ee160-110">El código siguiente devuelve un almacén aislado por usuario, dominio y ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ee160-110">The following code returns a store that is isolated by user, assembly, and domain.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 <span data-ttu-id="ee160-111">Puede usar el <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> método para especificar que un almacén se debe trasladar con un perfil de usuario móvil.</span><span class="sxs-lookup"><span data-stu-id="ee160-111">You can use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method to specify that a store should roam with a roaming user profile.</span></span> <span data-ttu-id="ee160-112">Para obtener más información sobre cómo configurar esta opción, vea [tipos de aislamiento](../../../docs/standard/io/types-of-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="ee160-112">For details on how to set this up, see [Types of Isolation](../../../docs/standard/io/types-of-isolation.md).</span></span>  
  
 <span data-ttu-id="ee160-113">Almacenes aislados que se obtienen del interior de distintos ensamblados son, de forma predeterminada, los almacenes diferentes.</span><span class="sxs-lookup"><span data-stu-id="ee160-113">Isolated stores obtained from within different assemblies are, by default, different stores.</span></span> <span data-ttu-id="ee160-114">Pueda acceder al almacén de otro ensamblado o dominio pasando de la evidencia de ensamblado o dominio de los parámetros de la <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> método.</span><span class="sxs-lookup"><span data-stu-id="ee160-114">You can access the store of a different assembly or domain by passing in the assembly or domain evidence in the parameters of the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="ee160-115">Esto requiere el permiso para tener acceso al almacenamiento aislado según la identidad de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ee160-115">This requires permission to access isolated storage by application domain identity.</span></span> <span data-ttu-id="ee160-116">Para obtener más información, consulte el <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> sobrecargas del método.</span><span class="sxs-lookup"><span data-stu-id="ee160-116">For more information, see the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method overloads.</span></span>  
  
 <span data-ttu-id="ee160-117">El <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, y <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> métodos devuelven un <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objeto.</span><span class="sxs-lookup"><span data-stu-id="ee160-117">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> methods return an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> object.</span></span> <span data-ttu-id="ee160-118">Para ayudarle a decidir qué tipo de aislamiento es más adecuado para su situación, vea [tipos de aislamiento](../../../docs/standard/io/types-of-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="ee160-118">To help you decide which isolation type is most appropriate for your situation, see [Types of Isolation](../../../docs/standard/io/types-of-isolation.md).</span></span> <span data-ttu-id="ee160-119">Cuando se tiene un objeto de archivo de almacenamiento aislado, puede usar los métodos de almacenamiento aislado para leer, escribir, crear y eliminar archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="ee160-119">When you have an isolated storage file object, you can use the isolated storage methods to read, write, create, and delete files and directories.</span></span>  
  
 <span data-ttu-id="ee160-120">No hay ningún mecanismo que evita que un código de pasar un <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objeto al código que no tiene suficientes derechos de acceso para obtener el almacén propiamente dicho.</span><span class="sxs-lookup"><span data-stu-id="ee160-120">There is no mechanism that prevents code from passing an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> object to code that does not have sufficient access to get the store itself.</span></span> <span data-ttu-id="ee160-121">Las identidades del dominio y ensamblado y los permisos de almacenamiento aislado sólo se comprueban cuando una referencia a un <xref:System.IO.IsolatedStorage.IsolatedStorage> objeto se obtiene, normalmente, en la <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, o <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> método.</span><span class="sxs-lookup"><span data-stu-id="ee160-121">Domain and assembly identities and isolated storage permissions are checked only when a reference to an <xref:System.IO.IsolatedStorage.IsolatedStorage> object is obtained, typically in the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, or <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="ee160-122">Protección de las referencias a <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objetos es, por lo tanto, la responsabilidad del código que utiliza estas referencias.</span><span class="sxs-lookup"><span data-stu-id="ee160-122">Protecting references to <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects is, therefore, the responsibility of the code that uses these references.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee160-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ee160-123">Example</span></span>  
 <span data-ttu-id="ee160-124">El código siguiente proporciona un ejemplo sencillo de una clase que obtiene un almacén aislado por usuario y ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ee160-124">The following code provides a simple example of a class obtaining a store that is isolated by user and assembly.</span></span> <span data-ttu-id="ee160-125">El código se puede cambiar para recuperar un almacén que está aislado por usuario, dominio y ensamblado agregando <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> a los argumentos que el <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> pasadas de método.</span><span class="sxs-lookup"><span data-stu-id="ee160-125">The code can be changed to retrieve a store that is isolated by user, domain, and assembly by adding <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> to the arguments that the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method passes.</span></span>  
  
 <span data-ttu-id="ee160-126">Después de ejecutar el código, puede confirmar que se creó un almacén escribiendo **StoreAdm /LIST** en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ee160-126">After you run the code, you can confirm that a store was created by typing **StoreAdm /LIST** at the command line.</span></span> <span data-ttu-id="ee160-127">Esta opción ejecuta la [herramienta almacenamiento aislado (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) y enumera todos los almacenes aislados actuales para el usuario.</span><span class="sxs-lookup"><span data-stu-id="ee160-127">This runs the [Isolated Storage tool (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) and lists all the current isolated stores for the user.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="ee160-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee160-128">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [<span data-ttu-id="ee160-129">Almacenamiento aislado</span><span class="sxs-lookup"><span data-stu-id="ee160-129">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
 [<span data-ttu-id="ee160-130">Tipos de aislamiento</span><span class="sxs-lookup"><span data-stu-id="ee160-130">Types of Isolation</span></span>](../../../docs/standard/io/types-of-isolation.md)  
 [<span data-ttu-id="ee160-131">Ensamblados en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="ee160-131">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
