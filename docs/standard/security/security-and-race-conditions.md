---
title: "Security and Race Conditions | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "security [.NET Framework], race conditions"
  - "race conditions"
  - "secure coding, race conditions"
  - "code security, race conditions"
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Security and Race Conditions
Otra de las áreas que preocupan es la posibilidad de los ataques mediante condiciones de carrera en las vulnerabilidades de seguridad.  Esto puede suceder de varias formas.  En los subtemas que aparecen a continuación se describen los principales riesgos que debe evitar el programador.  
  
## Condiciones de carrera en el método Dispose  
 Si el método **Dispose** de una clase \(para obtener más información, vea [Garbage Collection](../../../docs/standard/garbage-collection/index.md)\) no está sincronizado, es posible que el código de limpieza de **Dispose** se ejecute más de una vez, tal como se muestra en el ejemplo siguiente.  
  
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
  
 Como la implementación del método **Dispose** no está sincronizada, es posible que un primer subproceso llame a `Cleanup` y que, a continuación, lo haga un segundo subproceso antes de establecer el valor de `_myObj` en **null**.  En función de lo que ocurra cuando se ejecute el código `Cleanup`, esto puede convertirse en un problema de seguridad.  El problema principal con las implementaciones **Dispose** que no están sincronizadas es la utilización de identificadores de recursos como archivos.  Una eliminación incorrecta puede provocar la utilización del identificador erróneo, que con frecuencia crea puntos vulnerables en la seguridad.  
  
## Condiciones de carrera en constructores  
 En algunas aplicaciones, es posible que otros subprocesos tengan acceso a miembros de clase antes de que finalice la ejecución de sus constructores.  En el caso de que ocurra esto, debe revisar todos los constructores de clases para asegurarse de que no hay ningún problema de seguridad, o sincronizar los subprocesos si es necesario.  
  
## Condiciones de carrera con objetos en caché  
 El código que almacena en caché la información relacionada con la seguridad o que utiliza la operación [Assert](../../../docs/framework/misc/using-the-assert-method.md) de seguridad de acceso del código puede también ser vulnerable a condiciones de carrera si otras partes de la clase no están sincronizadas correctamente, como se muestra en el ejemplo siguiente.  
  
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
  
 Si hay otras rutas de acceso a `DoOtherWork` que se pueden llamar desde otro subproceso con el mismo objeto, un llamador que no sea de confianza puede conseguir pasar una petición.  
  
 Si el código detecta información relacionada con la seguridad, asegúrese de que revisa este punto vulnerable.  
  
## Condiciones de carrera en finalizadores  
 Las condiciones de carrera también se producen en un objeto que hace referencia a un recurso estático o no administrado que, posteriormente, libera en su finalizador.  Si hay varios objetos que comparten un recurso que se manipula en un finalizador de la clase, se deben sincronizar los accesos a ese recurso en todos los objetos.  
  
## Vea también  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)