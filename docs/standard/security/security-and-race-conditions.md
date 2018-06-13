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
ms.openlocfilehash: fdfc4d9e9ba3653bd1a762767e3c39a4f62e587a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582140"
---
# <a name="security-and-race-conditions"></a>Seguridad y condiciones de carrera
Otra área de preocupación es la posibilidad de vulnerabilidades de seguridad utilizado por las condiciones de carrera. Hay varias maneras en que esto puede ocurrir. Los subtemas siguientes describen algunos de los principales riesgos que debe evitar el programador.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Condiciones de carrera en el método Dispose  
 Si una clase **Dispose** (método) (para obtener más información, consulte [recolección](../../../docs/standard/garbage-collection/index.md)) no es sincronizada, es posible que ese código de limpieza dentro de **Dispose** se puede ejecutar más de vez, como se muestra en el ejemplo siguiente.  
  
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
    if( myObj != null )   
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 Dado que esto **Dispose** implementación no está sincronizada, es posible que `Cleanup` al primer subproceso y, a continuación, un segundo subproceso antes de llamar a `_myObj` está establecido en **null**. Si se trata de un problema de seguridad depende de lo que sucede cuando el `Cleanup` ejecuta el código. Un problema importante con sincronizado **Dispose** implementaciones implica el uso de identificadores de recursos como archivos. Eliminación incorrecta puede provocar el identificador incorrecto para usarse, lo que conduce a menudo a vulnerabilidades de seguridad.  
  
## <a name="race-conditions-in-constructors"></a>Condiciones de carrera en constructores  
 En algunas aplicaciones, es posible que otros subprocesos tener acceso a los miembros de clase antes de que finalice la ejecución sus constructores de clase. Debe revisar todos los constructores de clase para asegurarse de que no hay ningún problema de seguridad, si esto debería ocurrir o sincronizar los subprocesos si es necesario.  
  
## <a name="race-conditions-with-cached-objects"></a>Condiciones de carrera con objetos en caché  
 Código que almacena en caché información de seguridad o que utiliza la seguridad de acceso del código [Assert](../../../docs/framework/misc/using-the-assert-method.md) operación podría también ser vulnerable a condiciones de carrera si otras partes de la clase no están sincronizadas correctamente, como se muestra en el ejemplo siguiente.  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False()  
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
    if(SomeDemandPasses())   
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false();  
    }  
}  
void DoOtherWork()   
{  
    if( fCallersOK )   
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
  
 Si hay otras rutas de acceso a `DoOtherWork` que se pueden llamar desde otro subproceso con el mismo objeto, un llamador no es de confianza puede posponerse más allá de una petición.  
  
 Si el código almacena en caché información de seguridad, asegúrese de que revisarlo para esta vulnerabilidad.  
  
## <a name="race-conditions-in-finalizers"></a>Condiciones de anticipación en finalizadores  
 También pueden producirse condiciones de carrera en un objeto que hace referencia a un recurso estático o no administrado que, a continuación, libera en su finalizador. Si varios objetos que comparten un recurso que se ha manipulado de finalizador de la clase, los objetos deben sincronizar todo el acceso a ese recurso.  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de codificación segura](../../../docs/standard/security/secure-coding-guidelines.md)
