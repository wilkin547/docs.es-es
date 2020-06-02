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
# <a name="security-and-race-conditions"></a>Seguridad y condiciones de carrera
Otro área de preocupación es el potencial de los agujeros de seguridad aprovechados por las condiciones de carrera. Hay varias maneras en las que esto puede ocurrir. En los subtemas siguientes se describen algunos de los principales problemas que debe evitar el desarrollador.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Condiciones de carrera en el método Dispose  
 Si el método **Dispose** de una clase (para obtener más información, consulte recolección de [elementos no utilizados](../garbage-collection/index.md)) no está sincronizado, es posible que el código de limpieza dentro de **Dispose** se ejecute más de una vez, tal como se muestra en el ejemplo siguiente.  
  
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
  
 Dado que esta implementación de **Dispose** no está sincronizada, es posible que la `Cleanup` llame primero a un subproceso y, después, un segundo subproceso antes de `_myObj` que se establezca en **null**. Tanto si se trata de un problema de seguridad depende de lo que ocurre cuando `Cleanup` se ejecuta el código. Un problema importante con las implementaciones de **Dispose** no sincronizadas implica el uso de identificadores de recursos como los archivos. Una eliminación incorrecta puede provocar que se use un identificador incorrecto, lo que a menudo conduce a vulnerabilidades de seguridad.  
  
## <a name="race-conditions-in-constructors"></a>Condiciones de carrera en constructores  
 En algunas aplicaciones, es posible que otros subprocesos accedan a los miembros de clase antes de que sus constructores de clase se ejecuten por completo. Debe revisar todos los constructores de clase para asegurarse de que no hay ningún problema de seguridad si esto ocurre, o sincronizar los subprocesos si es necesario.  
  
## <a name="race-conditions-with-cached-objects"></a>Condiciones de carrera con objetos almacenados en caché  
 El código que almacena en memoria caché la información de seguridad o usa la operación de [aserción](../../framework/misc/using-the-assert-method.md) de seguridad de acceso del código también podría ser vulnerable a las condiciones de carrera si otras partes de la clase no se sincronizan correctamente, como se muestra en el ejemplo siguiente.  
  
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
  
 Si hay otras rutas de acceso a `DoOtherWork` las que se puede llamar desde otro subproceso con el mismo objeto, un llamador que no es de confianza puede posponerse después de una solicitud.  
  
 Si el código almacena en caché la información de seguridad, asegúrese de revisarla para ver esta vulnerabilidad.  
  
## <a name="race-conditions-in-finalizers"></a>Condiciones de carrera en finalizadores  
 También se pueden producir condiciones de carrera en un objeto que hace referencia a un recurso estático o no administrado que, a continuación, libera en su finalizador. Si varios objetos comparten un recurso que se manipula en el finalizador de una clase, los objetos deben sincronizar todo el acceso a ese recurso.  
  
## <a name="see-also"></a>Consulte también

- [Instrucciones de codificación segura](secure-coding-guidelines.md)
