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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57ceaedc7c38ae70a0db5a7fd584a765a7474aff
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44339356"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="210b4-102">Seguridad y condiciones de carrera</span><span class="sxs-lookup"><span data-stu-id="210b4-102">Security and Race Conditions</span></span>
<span data-ttu-id="210b4-103">Otra área de preocupación es la posibilidad de vulnerabilidades de seguridad utilizado por las condiciones de carrera.</span><span class="sxs-lookup"><span data-stu-id="210b4-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="210b4-104">Hay varias maneras en que esto puede ocurrir.</span><span class="sxs-lookup"><span data-stu-id="210b4-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="210b4-105">Los subtemas siguientes describen algunas de las dificultades principales que debe evitar el programador.</span><span class="sxs-lookup"><span data-stu-id="210b4-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="210b4-106">Condiciones de carrera en el método Dispose</span><span class="sxs-lookup"><span data-stu-id="210b4-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="210b4-107">Si una clase **Dispose** método (para obtener más información, consulte [recolección](../../../docs/standard/garbage-collection/index.md)) no es sincronizada, es posible que ese código de limpieza de **Dispose** se puede ejecutar más de vez, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="210b4-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="210b4-108">Dado que esto **Dispose** implementación no está sincronizada, es posible que `Cleanup` para ser llamado por el primer subproceso y, a continuación, un segundo subproceso antes de `_myObj` está establecido en **null**.</span><span class="sxs-lookup"><span data-stu-id="210b4-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="210b4-109">Si se trata de un problema de seguridad depende de lo que sucede cuando el `Cleanup` ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="210b4-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="210b4-110">Un problema importante que no sincronizadas **Dispose** implementaciones implica el uso de identificadores de recursos como archivos.</span><span class="sxs-lookup"><span data-stu-id="210b4-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="210b4-111">Eliminación incorrecta puede hacer que el controlador incorrecto que se usará, lo que conduce a menudo a las vulnerabilidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="210b4-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="210b4-112">Condiciones de carrera en constructores</span><span class="sxs-lookup"><span data-stu-id="210b4-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="210b4-113">En algunas aplicaciones, es posible que otros subprocesos tener acceso a los miembros de clase antes de que finalice la ejecución sus constructores de clases.</span><span class="sxs-lookup"><span data-stu-id="210b4-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="210b4-114">Debe revisar todos los constructores de clase para asegurarse de que no hay ningún problema de seguridad, si esto debería ocurrir o sincronizar los subprocesos si es necesario.</span><span class="sxs-lookup"><span data-stu-id="210b4-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="210b4-115">Condiciones de carrera con objetos en caché</span><span class="sxs-lookup"><span data-stu-id="210b4-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="210b4-116">Código que se almacena en caché información de seguridad o utiliza la seguridad de acceso del código [Assert](../../../docs/framework/misc/using-the-assert-method.md) operación podría también ser vulnerable a las condiciones de carrera si otras partes de la clase no están sincronizadas correctamente, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="210b4-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="210b4-117">Si hay otras rutas de acceso a `DoOtherWork` que pueden llamarse desde otro subproceso con el mismo objeto, un llamador de confianza se puede retrasar una petición.</span><span class="sxs-lookup"><span data-stu-id="210b4-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="210b4-118">Si el código almacena en caché información de seguridad, asegúrese de revisarlo para esta vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="210b4-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="210b4-119">Condiciones de carrera en los finalizadores</span><span class="sxs-lookup"><span data-stu-id="210b4-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="210b4-120">También pueden producirse condiciones de carrera en un objeto que hace referencia a un recurso estático o no administrado que se libera en su finalizador.</span><span class="sxs-lookup"><span data-stu-id="210b4-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="210b4-121">Si varios objetos que comparten un recurso que se ha manipulado de finalizador de la clase, los objetos deben sincronizar todo el acceso a ese recurso.</span><span class="sxs-lookup"><span data-stu-id="210b4-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="210b4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="210b4-122">See also</span></span>

- [<span data-ttu-id="210b4-123">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="210b4-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
