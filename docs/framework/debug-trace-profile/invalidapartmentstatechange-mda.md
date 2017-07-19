---
title: "invalidApartmentStateChange MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MDAs (managed debugging assistants), invalid apartment state"
  - "managed debugging assistants (MDAs), invalid apartment state"
  - "InvalidApartmentStateChange MDA"
  - "invalid apartment state changes"
  - "threading [.NET Framework], apartment states"
  - "apartment states"
  - "threading [.NET Framework], managed debugging assistants"
  - "COM apartment states"
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# invalidApartmentStateChange MDA
El asistente para la depuración administrada \(MDA\) de `invalidApartmentStateChange` se activa por cualquiera de estos dos problemas:  
  
-   Se intenta cambiar el estado de apartamento COM de un subproceso que ya ha inicializado COM en un estado de apartamento distinto.  
  
-   El estado de apartamento COM de un subproceso cambia inesperadamente.  
  
## Síntomas  
  
-   El estado de apartamento COM de un subproceso no corresponde a la solicitud.  Esto puede provocar que se utilicen proxy para componentes COM que tienen un modelo de subprocesos diferente del actual.  A su vez, esto puede dar lugar a que se produzca una excepción <xref:System.InvalidCastException> cuando se llama al objeto COM a través de interfaces no configuradas para el cálculo de referencias entre apartamentos.  
  
-   El estado de apartamento COM del subproceso es diferente del esperado.  Esto puede provocar una excepción <xref:System.Runtime.InteropServices.COMException> con el valor HRESULT de RPC\_E\_WRONG\_THREAD, así como una excepción <xref:System.InvalidCastException> al realizar las llamadas en un RCW \([Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md)\).  Esto también puede provocar que varios subprocesos obtengan acceso simultáneamente a algunos componentes COM de un único subproceso, lo que puede dar lugar a daños o a la pérdida de datos.  
  
## Motivo  
  
-   El subproceso se inicializó previamente en un estado de apartamento COM diferente.  Tenga en cuenta que el estado de apartamento de un subproceso se puede establecer explícita o implícitamente.  Las operaciones explícitas incluyen la propiedad <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=fullName> y los métodos <xref:System.Threading.Thread.SetApartmentState%2A> y <xref:System.Threading.Thread.TrySetApartmentState%2A>.  Un subproceso creado con el método <xref:System.Threading.Thread.Start%2A> se establece implícitamente en <xref:System.Threading.ApartmentState> a menos que se llame a <xref:System.Threading.Thread.SetApartmentState%2A> antes de que se produzca el subproceso.  El subproceso principal de la aplicación también se inicializa implícitamente en <xref:System.Threading.ApartmentState> a menos que se especifique el atributo <xref:System.STAThreadAttribute> en el método principal.  
  
-   En el subproceso se llama al método `CoUninitialize` \(o al método `CoInitializeEx`\) con un modelo de simultaneidad diferente.  
  
## Resolución  
 Establezca el estado de apartamento del subproceso antes de que éste comience a ejecutarse, o bien aplique el atributo <xref:System.STAThreadAttribute> o el atributo <xref:System.MTAThreadAttribute> al método principal de la aplicación.  
  
 Para el segundo motivo, lo ideal sería modificar el código que llama al método `CoUninitialize` para que retrase la llamada hasta que el subproceso esté a punto de terminar, no haya RCW y sus componentes COM subyacentes sigan siendo utilizados por el subproceso.  Sin embargo, si no es posible modificar el código que llama al método `CoUninitialize`, no deben utilizarse de este modo RCW de subprocesos sin inicializar.  
  
## Efecto en el Runtime  
 Este MDA no tiene efecto en el CLR.  
  
## Resultados  
 El estado de apartamento COM del subproceso actual y el estado que el código estaba intentando aplicar.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra una situación en la que se puede activar este MDA.  
  
```  
using System.Threading;  
namespace ApartmentStateMDA  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Thread.CurrentThread.SetApartmentState(ApartmentState.STA);  
        }  
    }  
}  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)