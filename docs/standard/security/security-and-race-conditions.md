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
ms.openlocfilehash: 09d8d0d6e85af04fe0fb00f53df408126012081e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186778"
---
# <a name="security-and-race-conditions"></a>Seguridad y condiciones de carrera
Otra área de preocupación es el potencial de agujeros de seguridad explotados por las condiciones de la carrera. Hay varias maneras en que esto podría suceder. Los subtemas que siguen describen algunos de los principales escollos que el desarrollador debe evitar.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Condiciones de carrera en el método Dispose  
 Si el método **Dispose** de una clase (para obtener más información, vea [Recolección](../../../docs/standard/garbage-collection/index.md)de elementos no utilizados ) no está sincronizado, es posible que el código de limpieza dentro de **Dispose** se pueda ejecutar más de una vez, como se muestra en el ejemplo siguiente.  
  
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
  
 Dado que esta implementación **de Dispose** `Cleanup` no está sincronizada, es posible que `_myObj` primero se llame por un subproceso y, a continuación, un segundo subproceso antes se establece en **null**. Si se trata de un problema `Cleanup` de seguridad depende de lo que sucede cuando se ejecuta el código. Un problema importante con las implementaciones De Sin sincronizar **implica** el uso de identificadores de recursos como archivos. La eliminación incorrecta puede hacer que se utilice el identificador incorrecto, lo que a menudo conduce a vulnerabilidades de seguridad.  
  
## <a name="race-conditions-in-constructors"></a>Condiciones de carrera en constructores  
 En algunas aplicaciones, es posible que otros subprocesos tengan acceso a los miembros de clase antes de que sus constructores de clase se hayan ejecutado por completo. Debe revisar todos los constructores de clase para asegurarse de que no hay problemas de seguridad si esto debe suceder, o sincronizar subprocesos si es necesario.  
  
## <a name="race-conditions-with-cached-objects"></a>Condiciones de carrera con objetos almacenados en caché  
 El código que almacena en caché la información de seguridad o usa la operación [Assert](../../../docs/framework/misc/using-the-assert-method.md) de seguridad de acceso de código también puede ser vulnerable a las condiciones de carrera si otras partes de la clase no se sincronizan adecuadamente, como se muestra en el ejemplo siguiente.  
  
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
  
 Si hay otras `DoOtherWork` rutas de acceso a que se puede llamar desde otro subproceso con el mismo objeto, un llamador que no es de confianza puede pasar una demanda.  
  
 Si el código almacena en caché la información de seguridad, asegúrese de revisarla para ver esta vulnerabilidad.  
  
## <a name="race-conditions-in-finalizers"></a>Condiciones de carrera en finalizadores  
 Las condiciones de carrera también pueden producirse en un objeto que hace referencia a un recurso estático o no administrado que, a continuación, libera en su finalizador. Si varios objetos comparten un recurso que se manipula en el finalizador de una clase, los objetos deben sincronizar todo el acceso a ese recurso.  
  
## <a name="see-also"></a>Consulte también

- [Instrucciones de codificación segura](../../../docs/standard/security/secure-coding-guidelines.md)
