---
title: Seguridad y condiciones de carrera
'description:': Describes pitfalls to avoid around security holes exploited by race conditions, including dispose methods, constructors, cached objects, and finalizers.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
ms.openlocfilehash: 715bf240a5f7f44ba3f914ad6788631074aa41b2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291024"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="9aff9-102">Seguridad y condiciones de carrera</span><span class="sxs-lookup"><span data-stu-id="9aff9-102">Security and Race Conditions</span></span>
<span data-ttu-id="9aff9-103">Otro área de preocupación es el potencial de los agujeros de seguridad aprovechados por las condiciones de carrera.</span><span class="sxs-lookup"><span data-stu-id="9aff9-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="9aff9-104">Hay varias maneras en las que esto puede ocurrir.</span><span class="sxs-lookup"><span data-stu-id="9aff9-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="9aff9-105">En los subtemas siguientes se describen algunos de los principales problemas que debe evitar el desarrollador.</span><span class="sxs-lookup"><span data-stu-id="9aff9-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="9aff9-106">Condiciones de carrera en el método Dispose</span><span class="sxs-lookup"><span data-stu-id="9aff9-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="9aff9-107">Si el método **Dispose** de una clase (para obtener más información, consulte recolección de [elementos no utilizados](../garbage-collection/index.md)) no está sincronizado, es posible que el código de limpieza dentro de **Dispose** se ejecute más de una vez, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9aff9-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
```vb  
Sub Dispose()  
    If Not (myObj Is Nothing) Then  
       Cleanup(myObj)  
       myObj = Nothing  
    End If  
End Sub  
```  
  
```csharp  
void Dispose()
{  
    if (myObj != null)
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 <span data-ttu-id="9aff9-108">Dado que esta implementación de **Dispose** no está sincronizada, es posible que la `Cleanup` llame primero a un subproceso y, después, un segundo subproceso antes de `_myObj` que se establezca en **null**.</span><span class="sxs-lookup"><span data-stu-id="9aff9-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="9aff9-109">Tanto si se trata de un problema de seguridad depende de lo que ocurre cuando `Cleanup` se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="9aff9-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="9aff9-110">Un problema importante con las implementaciones de **Dispose** no sincronizadas implica el uso de identificadores de recursos como los archivos.</span><span class="sxs-lookup"><span data-stu-id="9aff9-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="9aff9-111">Una eliminación incorrecta puede provocar que se use un identificador incorrecto, lo que a menudo conduce a vulnerabilidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9aff9-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="9aff9-112">Condiciones de carrera en constructores</span><span class="sxs-lookup"><span data-stu-id="9aff9-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="9aff9-113">En algunas aplicaciones, es posible que otros subprocesos accedan a los miembros de clase antes de que sus constructores de clase se ejecuten por completo.</span><span class="sxs-lookup"><span data-stu-id="9aff9-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="9aff9-114">Debe revisar todos los constructores de clase para asegurarse de que no hay ningún problema de seguridad si esto ocurre, o sincronizar los subprocesos si es necesario.</span><span class="sxs-lookup"><span data-stu-id="9aff9-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="9aff9-115">Condiciones de carrera con objetos almacenados en caché</span><span class="sxs-lookup"><span data-stu-id="9aff9-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="9aff9-116">El código que almacena en memoria caché la información de seguridad o usa la operación de [aserción](../../framework/misc/using-the-assert-method.md) de seguridad de acceso del código también podría ser vulnerable a las condiciones de carrera si otras partes de la clase no se sincronizan correctamente, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9aff9-116">Code that caches security information or uses the code access security [Assert](../../framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False  
    End If  
End Sub  
  
Sub DoOtherWork()  
    If fCallersOK Then  
        DoSomethingTrusted()  
    Else  
        DemandSomething()  
        DoSomethingTrusted()  
    End If  
End Sub  
```  
  
```csharp  
void SomeSecureFunction()
{  
    if (SomeDemandPasses())
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false;  
    }  
}  
void DoOtherWork()
{  
    if (fCallersOK)
    {  
        DoSomethingTrusted();  
    }  
    else
    {  
        DemandSomething();  
        DoSomethingTrusted();  
    }  
}  
```  
  
 <span data-ttu-id="9aff9-117">Si hay otras rutas de acceso a `DoOtherWork` las que se puede llamar desde otro subproceso con el mismo objeto, un llamador que no es de confianza puede posponerse después de una solicitud.</span><span class="sxs-lookup"><span data-stu-id="9aff9-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="9aff9-118">Si el código almacena en caché la información de seguridad, asegúrese de revisarla para ver esta vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="9aff9-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="9aff9-119">Condiciones de carrera en finalizadores</span><span class="sxs-lookup"><span data-stu-id="9aff9-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="9aff9-120">También se pueden producir condiciones de carrera en un objeto que hace referencia a un recurso estático o no administrado que, a continuación, libera en su finalizador.</span><span class="sxs-lookup"><span data-stu-id="9aff9-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="9aff9-121">Si varios objetos comparten un recurso que se manipula en el finalizador de una clase, los objetos deben sincronizar todo el acceso a ese recurso.</span><span class="sxs-lookup"><span data-stu-id="9aff9-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aff9-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9aff9-122">See also</span></span>

- [<span data-ttu-id="9aff9-123">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="9aff9-123">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)
