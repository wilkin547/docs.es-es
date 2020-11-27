---
title: MDA de invalidApartmentStateChange
description: Obtenga información sobre el Asistente para la depuración administrada (MDA) de invalidApartmentStateChange en .NET, que se activa si hay problemas con el estado de contenedor COM.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid apartment state
- managed debugging assistants (MDAs), invalid apartment state
- InvalidApartmentStateChange MDA
- invalid apartment state changes
- threading [.NET Framework], apartment states
- apartment states
- threading [.NET Framework], managed debugging assistants
- COM apartment states
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
ms.openlocfilehash: db55e3ac2d6862d008013abef0f09f67213d9faa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272753"
---
# <a name="invalidapartmentstatechange-mda"></a>MDA de invalidApartmentStateChange

El Asistente para la depuración administrada (MDS) `invalidApartmentStateChange` se activa por cualquiera de estos dos problemas:  
  
- Se realiza un intento de cambiar el estado de contenedor COM de un subproceso que ya se ha inicializado por COM a un estado de contenedor diferente.  
  
- El estado de contenedor COM de un subproceso cambia de forma inesperada.  
  
## <a name="symptoms"></a>Síntomas  
  
- El estado de contenedor COM de un subproceso no es el que se solicitó. Esto puede provocar que se usen servidores proxy para los componentes COM que tienen un modelo de subprocesos diferente del actual. A su vez, esto puede hacer que se inicie una excepción <xref:System.InvalidCastException> al llamar al objeto COM a través de interfaces que no están configuradas para la serialización entre contenedores.  
  
- El estado de contenedor COM del subproceso es diferente de lo esperado. Esto puede causar una excepción <xref:System.Runtime.InteropServices.COMException> con un valor HRESULT de RPC_E_WRONG_THREAD, así como una excepción <xref:System.InvalidCastException> cuando se realizan llamadas en un [contenedor RCW](../../standard/native-interop/runtime-callable-wrapper.md). Esto puede hacer que varios subprocesos tengan acceso al mismo tiempo a algunos componentes COM de un único subproceso, lo que puede provocar daños o pérdida de datos.  
  
## <a name="cause"></a>Causa  
  
- El subproceso se inicializó previamente a un estado de contenedor COM diferente. Tenga en cuenta que el estado de contenedor de un subproceso se puede establecer de forma explícita o implícita. Las operaciones explícitas incluyen la propiedad <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> y los métodos <xref:System.Threading.Thread.SetApartmentState%2A> y <xref:System.Threading.Thread.TrySetApartmentState%2A>. Un subproceso creado mediante el método <xref:System.Threading.Thread.Start%2A> se establece implícitamente en <xref:System.Threading.ApartmentState.MTA> a menos que se llame a <xref:System.Threading.Thread.SetApartmentState%2A> antes de iniciar el subproceso. El subproceso principal de la aplicación también se inicializa implícitamente en <xref:System.Threading.ApartmentState.MTA> a menos que se especifique el atributo <xref:System.STAThreadAttribute> en el método principal.  
  
- El método `CoUninitialize` (o el método `CoInitializeEx`) con un modelo de simultaneidad diferente se llama en el subproceso.  
  
## <a name="resolution"></a>Solución  

 Establecer el estado de contenedor del subproceso antes de que empiece a ejecutarse, o aplicar el atributo <xref:System.STAThreadAttribute> o <xref:System.MTAThreadAttribute> al método principal de la aplicación.  
  
 Para la segunda causa, idealmente el código que llama al método `CoUninitialize` debe modificarse para retrasar la llamada hasta que el subproceso esté a punto de terminar y no haya ningún RCW, y sus componentes COM subyacentes sigan en uso en el subproceso. Pero si no es posible modificar el código que llama al método `CoUninitialize`, entonces no deben usarse contenedores RCW desde los subprocesos sin inicializar de esta manera.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  

 Este MDA no tiene ningún efecto en el CLR.  
  
## <a name="output"></a>Resultados  

 El estado de contenedor COM del subproceso actual y el estado que el código intentaba aplicar.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo de código siguiente se muestra una situación que puede activar este MDA.  
  
```csharp
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización de interoperabilidad](../interop/interop-marshaling.md)
