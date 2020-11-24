---
title: 'Cómo: Prever condiciones de espacio insuficiente con almacenamiento aislado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data stores, quotas
- isolated storage, quotas
- quantity of isolated storage used
- limit on isolated storage used
- stores, quotas
- stores, out of space conditions
- data storage using isolated storage, quotas
- storing data using isolated storage, quotas
- space remaining in isolated storage
- data stores, out of space conditions
- storing data using isolated storage, out of space conditions
- quotas for isolated storage
- isolated storage, out of space conditions
- data storage using isolated storage, out of space conditions
ms.assetid: e35d4535-3732-421e-b1a3-37412e036145
ms.openlocfilehash: c8052030cdc385fc54852bb8ec48c783f2ee5bc4
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830849"
---
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a><span data-ttu-id="22e10-102">Cómo: Prever condiciones de espacio insuficiente con almacenamiento aislado</span><span class="sxs-lookup"><span data-stu-id="22e10-102">How to: Anticipate Out-of-Space Conditions with Isolated Storage</span></span>

<span data-ttu-id="22e10-103">El código que usa el almacenamiento aislado está restringido por una [cuota](isolated-storage.md#quotas) que especifica el tamaño máximo para el compartimiento de datos en que se encuentran los directorios y los archivos del almacenamiento aislado.</span><span class="sxs-lookup"><span data-stu-id="22e10-103">Code that uses isolated storage is constrained by a [quota](isolated-storage.md#quotas) that specifies the maximum size for the data compartment in which isolated storage files and directories exist.</span></span> <span data-ttu-id="22e10-104">La cuota se define mediante la directiva de seguridad y la pueden configurar los administradores.</span><span class="sxs-lookup"><span data-stu-id="22e10-104">The quota is defined by security policy and is configurable by administrators.</span></span> <span data-ttu-id="22e10-105">Si se supera el tamaño máximo permitido al intentar escribir datos, se genera la excepción <xref:System.IO.IsolatedStorage.IsolatedStorageException> y se produce un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="22e10-105">If the maximum allowed size is exceeded when you try to write data, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown and the operation fails.</span></span> <span data-ttu-id="22e10-106">Esto ayuda a evitar los ataques de denegación de servicio malintencionados que pudieron provocar que la aplicación rechazara solicitudes porque se llenara el almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="22e10-106">This helps prevent malicious denial-of-service attacks that could cause the application to refuse requests because data storage is filled.</span></span>

<span data-ttu-id="22e10-107">Para ayudarlo a determinar si un intento de escritura determinado puede presentar errores por este motivo, la clase <xref:System.IO.IsolatedStorage.IsolatedStorage> proporciona tres propiedades de solo lectura: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A> y <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.</span><span class="sxs-lookup"><span data-stu-id="22e10-107">To help you determine whether a given write attempt is likely to fail for this reason, the <xref:System.IO.IsolatedStorage.IsolatedStorage> class provides three read-only properties: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, and <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.</span></span> <span data-ttu-id="22e10-108">Puede utilizar estas propiedades para determinar si escribir en el almacén hará que se supere el tamaño máximo permitido del almacén.</span><span class="sxs-lookup"><span data-stu-id="22e10-108">You can use these properties to determine whether writing to the store will cause the maximum allowed size of the store to be exceeded.</span></span> <span data-ttu-id="22e10-109">Tenga en cuenta que se puede acceder al almacenamiento aislado de forma simultánea; por tanto, al calcular la cantidad de almacenamiento restante, el tiempo durante el cual se intenta escribir en el almacén podría consumir el espacio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="22e10-109">Keep in mind that isolated storage can be accessed concurrently; therefore, when you compute the amount of remaining storage, the storage space could be consumed by the time you try to write to the store.</span></span> <span data-ttu-id="22e10-110">Sin embargo, puede usar el tamaño máximo del almacén para ayudar a determinar si el límite superior del almacenamiento disponible está a punto de alcanzarse.</span><span class="sxs-lookup"><span data-stu-id="22e10-110">However, you can use the maximum size of the store to help determine whether the upper limit on available storage is about to be reached.</span></span>

<span data-ttu-id="22e10-111">La propiedad <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> depende de la evidencia del ensamblado para que funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="22e10-111">The <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> property depends on evidence from the assembly to work properly.</span></span> <span data-ttu-id="22e10-112">Por este motivo, debe recuperar esta propiedad solo en objetos <xref:System.IO.IsolatedStorage.IsolatedStorageFile> que se crearon con los métodos <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> o <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.</span><span class="sxs-lookup"><span data-stu-id="22e10-112">For this reason, you should retrieve this property only on <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that were created by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, or <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="22e10-113">Los objetos <xref:System.IO.IsolatedStorage.IsolatedStorageFile> creados de otra forma (por ejemplo, los objetos devueltos por el método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>) no devolverán un tamaño máximo preciso.</span><span class="sxs-lookup"><span data-stu-id="22e10-113"><xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that were created in any other way (for example, objects that were returned from the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method) will not return an accurate maximum size.</span></span>

## <a name="example"></a><span data-ttu-id="22e10-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22e10-114">Example</span></span>

<span data-ttu-id="22e10-115">En el ejemplo de código siguiente se obtiene un almacén aislado, se crean algunos archivos y se recupera la propiedad <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>.</span><span class="sxs-lookup"><span data-stu-id="22e10-115">The following code example obtains an isolated store, creates a few files, and retrieves the <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> property.</span></span> <span data-ttu-id="22e10-116">El espacio restante se notifica en bytes.</span><span class="sxs-lookup"><span data-stu-id="22e10-116">The remaining space is reported in bytes.</span></span>

[!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
[!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
[!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]

## <a name="see-also"></a><span data-ttu-id="22e10-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="22e10-117">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [<span data-ttu-id="22e10-118">Almacenamiento aislado</span><span class="sxs-lookup"><span data-stu-id="22e10-118">Isolated Storage</span></span>](isolated-storage.md)
- [<span data-ttu-id="22e10-119">Cómo: Obtener los almacenes de almacenamiento aislado</span><span class="sxs-lookup"><span data-stu-id="22e10-119">How to: Obtain Stores for Isolated Storage</span></span>](how-to-obtain-stores-for-isolated-storage.md)
