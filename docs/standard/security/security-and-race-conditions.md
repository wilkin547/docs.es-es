---
title: Seguridad y condiciones de carrera
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
ms.openlocfilehash: 8980122acdd069bc840aa09129483a1cb9a379fd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705878"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="1591b-102">Seguridad y condiciones de carrera</span><span class="sxs-lookup"><span data-stu-id="1591b-102">Security and Race Conditions</span></span>
<span data-ttu-id="1591b-103">Otro área de preocupación es el potencial de los agujeros de seguridad aprovechados por las condiciones de carrera.</span><span class="sxs-lookup"><span data-stu-id="1591b-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="1591b-104">Hay varias maneras en las que esto puede ocurrir.</span><span class="sxs-lookup"><span data-stu-id="1591b-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="1591b-105">En los subtemas siguientes se describen algunos de los principales problemas que debe evitar el desarrollador.</span><span class="sxs-lookup"><span data-stu-id="1591b-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="1591b-106">Condiciones de carrera en el método Dispose</span><span class="sxs-lookup"><span data-stu-id="1591b-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="1591b-107">Si el método **Dispose** de una clase (para obtener más información, consulte recolección de [elementos no utilizados](../../../docs/standard/garbage-collection/index.md)) no está sincronizado, es posible que el código de limpieza dentro de **Dispose** se ejecute más de una vez, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1591b-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="1591b-108">Dado que esta implementación de **Dispose** no está sincronizada, es posible que se llame a `Cleanup` en el primer subproceso y, después, a un segundo subproceso antes de que `_myObj` se establezca en **null**.</span><span class="sxs-lookup"><span data-stu-id="1591b-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="1591b-109">Tanto si se trata de un problema de seguridad depende de lo que ocurre cuando se ejecuta el código `Cleanup`.</span><span class="sxs-lookup"><span data-stu-id="1591b-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="1591b-110">Un problema importante con las implementaciones de **Dispose** no sincronizadas implica el uso de identificadores de recursos como los archivos.</span><span class="sxs-lookup"><span data-stu-id="1591b-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="1591b-111">Una eliminación incorrecta puede provocar que se use un identificador incorrecto, lo que a menudo conduce a vulnerabilidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1591b-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="1591b-112">Condiciones de carrera en constructores</span><span class="sxs-lookup"><span data-stu-id="1591b-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="1591b-113">En algunas aplicaciones, es posible que otros subprocesos accedan a los miembros de clase antes de que sus constructores de clase se ejecuten por completo.</span><span class="sxs-lookup"><span data-stu-id="1591b-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="1591b-114">Debe revisar todos los constructores de clase para asegurarse de que no hay ningún problema de seguridad si esto ocurre, o sincronizar los subprocesos si es necesario.</span><span class="sxs-lookup"><span data-stu-id="1591b-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="1591b-115">Condiciones de carrera con objetos almacenados en caché</span><span class="sxs-lookup"><span data-stu-id="1591b-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="1591b-116">El código que almacena en memoria caché la información de seguridad o usa la operación de [aserción](../../../docs/framework/misc/using-the-assert-method.md) de seguridad de acceso del código también podría ser vulnerable a las condiciones de carrera si otras partes de la clase no se sincronizan correctamente, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1591b-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="1591b-117">Si hay otras rutas de acceso a `DoOtherWork` a las que se puede llamar desde otro subproceso con el mismo objeto, un llamador que no es de confianza puede posponerse después de una solicitud.</span><span class="sxs-lookup"><span data-stu-id="1591b-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="1591b-118">Si el código almacena en caché la información de seguridad, asegúrese de revisarla para ver esta vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="1591b-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="1591b-119">Condiciones de carrera en finalizadores</span><span class="sxs-lookup"><span data-stu-id="1591b-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="1591b-120">También se pueden producir condiciones de carrera en un objeto que hace referencia a un recurso estático o no administrado que, a continuación, libera en su finalizador.</span><span class="sxs-lookup"><span data-stu-id="1591b-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="1591b-121">Si varios objetos comparten un recurso que se manipula en el finalizador de una clase, los objetos deben sincronizar todo el acceso a ese recurso.</span><span class="sxs-lookup"><span data-stu-id="1591b-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1591b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="1591b-122">See also</span></span>

- [<span data-ttu-id="1591b-123">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="1591b-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
