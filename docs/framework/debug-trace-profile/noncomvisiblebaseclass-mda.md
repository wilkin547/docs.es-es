---
title: MDA de nonComVisibleBaseClass
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- visible classes
- managed debugging assistants (MDAs), COM visible classes
- nonComVisibleBaseClass MDA
- COM visible classes
- QueryInterface call failures
- MDAs (managed debugging assistants), COM visible classes
ms.assetid: 9ec1af27-604b-477e-9ee2-e833eb10d3ce
caps.latest.revision: 9
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7f6da0e4a2046ac80a35894383f732eb266b8459
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="noncomvisiblebaseclass-mda"></a>MDA de nonComVisibleBaseClass
El Asistente para la depuración administrada (MDA) `nonComVisibleBaseClass` se activa cuando se realiza una llamada a `QueryInterface` desde código no administrado o nativo en el contenedor CCW de una clase administrada visible para COM que deriva de una clase base que no es visible para COM.  La llamada a `QueryInterface` hace que el MDA se active solo cuando la llamada solicita la interfaz de clase o la interfaz predeterminado `IDispatch` de la clase administrada visible para COM.  El MDA no se activa cuando `QueryInterface` es para una interfaz explícita que tiene aplicado el atributo <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> y se implementa explícitamente la clase visible para COM.  
  
## <a name="symptoms"></a>Síntomas  
 Una llamada a `QueryInterface` que se realiza desde código nativo produce el error COR_E_INVALIDOPERATION HRESULT.  El HRESULT podría deberse a que CLR no permite llamadas a  `QueryInterface` que producirían la activación de este MDA.  
  
## <a name="cause"></a>Motivo  
 CLR no puede permitir llamadas a `QueryInterface` para la interfaz de clase o la interfaz `IDispatch` predeterminada de una clase visible para COM que deriva de una clase que no es visible para COM debido a posibles problemas de versiones.  Por ejemplo, si se agregan miembros públicos a la clase base que no es visible para COM, los clientes COM existentes que usan la clase derivada podrían interrumpirse porque la vtable de la clase derivada, que contiene los miembros de clase base, se vería alterada por ese cambio.  Las interfaces explícitas expuestas a COM no tienen este problema porque no incluyen los miembros base de las interfaces en la vtable.  
  
## <a name="resolution"></a>Resolución  
 No exponga la interfaz de clase. Defina una interfaz explícita y aplíquele el atributo <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## <a name="output"></a>Salida  
 El siguiente es un mensaje de ejemplo de una llamada a `QueryInterface` en una clase visible para COM `Derived` que deriva de una clase no visible para COM `Base`.  
  
```  
A QueryInterface call was made requesting the class interface of COM   
visible managed class 'Derived'. However since this class derives from   
non COM visible class 'Base', the QueryInterface call will fail. This   
is done to prevent the non COM visible base class from being   
constrained by the COM versioning rules.   
```  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <nonComVisibleBaseClass />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnóstico de errores con asistentes para la depuración administrada](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Serialización de interoperabilidad](../../../docs/framework/interop/interop-marshaling.md)

