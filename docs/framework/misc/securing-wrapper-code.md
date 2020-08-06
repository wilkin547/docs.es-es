---
title: Insertar en el repositorio código de contenedor
description: Revise cómo proteger el código de contenedor, que puede abrir un conjunto único de puntos débiles de seguridad, especialmente si el contenedor tiene una mayor confianza que el código que lo usa.
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], wrapper code
- wrapper code, securing
- secure coding, wrapper code
- code security, wrapper code
ms.assetid: 1df6c516-5bba-48bd-b450-1070e04b7389
ms.openlocfilehash: f448cbf55f3ad992ba9dcc53d5be70b364038744
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855756"
---
# <a name="securing-wrapper-code"></a>Insertar en el repositorio código de contenedor

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 El código de contenedor, especialmente cuando el contenedor tiene mayor confianza que el código que lo usa, puede descubrir un conjunto único de vulnerabilidades de seguridad. Todo lo hecho en nombre de un llamador, cuyos permisos limitados no se incluyen en la comprobación de seguridad adecuada, es una vulnerabilidad potencial que puede ser aprovechada.  
  
 No habilite nunca nada a través del contenedor que el llamador no pueda hacer él mismo. Esto es especialmente peligroso cuando se realiza una acción que implica una comprobación de seguridad limitada, en lugar de una petición de recorrido de pila completo. Si hay comprobaciones de nivel único implicadas, la interposición de código de contenedor entre el llamador real y el elemento de la API en cuestión puede hacer fácilmente que la comprobación de seguridad tenga éxito cuando no debería tenerlo, con el consiguiente debilitamiento de la seguridad.  
  
## <a name="delegates"></a>Delegados  
 La seguridad de los delegados difiere entre las versiones de .NET Framework.  En esta sección se describe el comportamiento de los distintos delegados y las consideraciones de seguridad asociadas.  
  
### <a name="in-version-10-and-11-of-the-net-framework"></a>En las versiones 1.0 y 1.1 de .NET Framework  
 Las versiones 1.0 y 1.1 de .NET Framework llevan a cabo las siguientes acciones de seguridad frente a un creador de delegado y un llamador de delegado.  
  
- Cuando se crea un delegado, las peticiones de vínculo de seguridad en el método de destino del delegado se realizan en el conjunto de permisos del creador del delegado.  El incumplimiento de la acción de seguridad produce un <xref:System.Security.SecurityException>.  
  
- Cuando se invoca el delegado, se realiza cualquier petición de seguridad existente en el llamador del delegado.  
  
 Siempre que su código tome un <xref:System.Delegate> de un código de menor confianza que pueda llamarlo, asegúrese de que no habilita al código de menor confianza para que aumente sus permisos. Si toma un delegado y lo usa más adelante, el código que creó el delegado no está en la pila de llamadas y sus permisos no se probarán si el código que está en el delegado o bajo el delegado intenta una operación protegida. Si su código y el código del llamador tienen privilegios más elevados que el creador, el creador puede organizar la ruta de la llamada sin formar parte de la pila de llamadas.  
  
### <a name="in-version-20-and-later-versions-of-the-net-framework"></a>En la versión 2,0 y versiones posteriores del .NET Framework  
 A diferencia de las versiones anteriores, la versión 2,0 y las versiones posteriores del .NET Framework realiza una acción de seguridad en el creador del delegado cuando se crea y se llama al delegado.  
  
- Cuando se crea un delegado, las peticiones de vínculo de seguridad en el método de destino del delegado se realizan en el conjunto de permisos del creador del delegado.  El incumplimiento de la acción de seguridad produce un <xref:System.Security.SecurityException>.  
  
- El conjunto de permisos del creador del delegado también se captura durante la creación del delegado y se almacena con dicho delegado.  
  
- Cuando se invoca el delegado, el conjunto de permisos capturado del creador del delegado se evalúa en primer lugar frente a las peticiones en el contexto actual si el creador del delegado y el llamador pertenecen a distintos ensamblados.  A continuación, se realizan todas las peticiones de seguridad existentes en el llamador del delegado.  
  
## <a name="link-demands-and-wrappers"></a>Peticiones de vínculo y contenedores  
 Se ha reforzado un caso especial de protección con peticiones de vínculo en la infraestructura de seguridad, pero sigue siendo una fuente de posibles vulnerabilidades en el código.  
  
 Si el código de plena confianza llama a una propiedad, un evento o un método protegido por [LinkDemand](link-demands.md), la llamada se realiza correctamente si se cumple la comprobación del permiso **LinkDemand** para el llamador. Además, si el código de plena confianza expone una clase que toma el nombre de una propiedad y llama a su descriptor de acceso **Get** mediante reflexión, esa llamada al descriptor de acceso **Get** se realiza correctamente aunque el código de usuario no tenga el derecho a obtener acceso a esta propiedad. Esto se debe a que **LinkDemand** comprueba solo el llamador inmediato, que es el código de plena confianza. Básicamente, el código de plena confianza realiza una llamada privilegiada en nombre del código de usuario sin comprobar si el código de usuario tiene derecho a hacer esa llamada.  
  
 Para ayudar a evitar este tipo de carencias de seguridad, el Common Language Runtime extiende la comprobación a una demanda completa de recorrido de pila en cualquier llamada indirecta a un método, constructor, propiedad o evento protegido por una **LinkDemand**. Esta protección conlleva algunos costos de rendimiento y cambia la semántica de la comprobación de seguridad; la petición de recorrido de pila completo puede provocar errores que no se producirían en la comprobación rápida de un nivel.  
  
## <a name="assembly-loading-wrappers"></a>Contenedores de carga de ensamblados  
 Varios de los métodos usados para cargar código administrado, incluido <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, cargan ensamblados con la evidencia del llamador. Si encapsula cualquiera de estos métodos, el sistema de seguridad podría usar, para cargar los ensamblados, el permiso concedido al código en lugar de los permisos del llamador para el contenedor. No permita que el código de menos confianza cargue el código al que se conceden permisos superiores a los del autor de la llamada al contenedor.  
  
 Cualquier código que tenga plena confianza o una confianza significativamente mayor que la de un posible llamador (incluido un llamador con nivel de permisos de Internet) podría debilitar la seguridad de esta manera. Si el código tiene un método público que toma una matriz de bytes y la pasa a **Assembly. Load**, con lo que se crea un ensamblado en nombre del llamador, se podría interrumpir la seguridad.  
  
 Este problema se aplica a los siguientes elementos de la API:  
  
- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>  
  
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>  
  
## <a name="demand-vs-linkdemand"></a>Demand versus LinkDemand  
 La seguridad declarativa ofrece dos tipos de comprobaciones de seguridad que son similares pero realizan comprobaciones diferentes. Es conveniente comprender ambos formatos, ya que la opción equivocada puede dar lugar a una pérdida de rendimiento o seguridad débil.  
  
 La seguridad declarativa ofrece las siguientes comprobaciones de seguridad:  
  
- <xref:System.Security.Permissions.SecurityAction.Demand> especifica el recorrido de pila de seguridad de acceso del código. Todos los llamadores de la pila deben tener el permiso o la identidad especificados para pasar. La **demanda** se produce en cada llamada porque la pila puede contener diferentes llamadores. Si llama a un método repetidas veces, esta comprobación de seguridad se realiza cada vez. La **demanda** es una buena protección contra los ataques por Señuelos; se detectará un código no autorizado que intente obtener acceso a través de él.  
  
- [LinkDemand](link-demands.md) se produce en el momento de la compilación Just-in-Time (JIT) y comprueba solo el llamador inmediato. Esta comprobación de seguridad no comprueba el llamador del llamador. Una vez que se supera esta comprobación, no hay ninguna seguridad adicional posterior independientemente de las veces que el llamador pueda llamar. Sin embargo, tampoco hay protección contra los ataques por señuelo. Con **LinkDemand**, cualquier código que pase la prueba y puede hacer referencia a su código podría interrumpir la seguridad permitiendo que el código malintencionado llame a mediante el código autorizado. Por lo tanto, no use **LinkDemand** a menos que todos los puntos débiles posibles se puedan evitar con detalle.  
  
    > [!NOTE]
    > En el .NET Framework 4, las peticiones de vínculo se han reemplazado por el <xref:System.Security.SecurityCriticalAttribute> atributo de los <xref:System.Security.SecurityRuleSet.Level2> ensamblados. <xref:System.Security.SecurityCriticalAttribute>Es equivalente a una petición de vínculo para la plena confianza; sin embargo, también afecta a las reglas de herencia. Para obtener más información sobre este cambio, vea [código transparente en seguridad, nivel 2](security-transparent-code-level-2.md).  
  
 Las precauciones adicionales necesarias cuando se usa **LinkDemand** deben programarse individualmente. el sistema de seguridad puede ayudar en la aplicación. Cualquier error abre una vulnerabilidad en la seguridad. Todo código autorizado que use su código debe hacerse responsable de implementar seguridad adicional mediante lo siguiente:  
  
- Restringir el acceso del código de llamada a la clase o al ensamblado.  
  
- Colocar en el código de llamada las mismas comprobaciones de seguridad que aparecen en el código al que se llama y obligar a sus llamadores a hacer lo mismo. Por ejemplo, si escribe código que llama a un método que está protegido con una **LinkDemand** para el <xref:System.Security.Permissions.SecurityPermission> con la <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> marca especificada, el método debe realizar también una **LinkDemand** (o **Demand**, que es más seguro) para este permiso. La excepción es si el código usa el método protegido con **LinkDemand**de una forma limitada que decida que es seguro, dados otros mecanismos de protección de seguridad (como las demandas) en el código. En este caso excepcional, el llamador es el responsable de debilitar la protección de seguridad en el código subyacente.  
  
- Garantizar que los llamadores de su código no pueden engañar al código para que llame al código protegido en su nombre. En otras palabras, los llamadores no pueden forzar al código autorizado para pasar parámetros específicos al código protegido o para obtener resultados de él.  
  
### <a name="interfaces-and-link-demands"></a>Interfaces y peticiones de vínculo  
 Si un método virtual, propiedad o evento con **LinkDemand** invalida un método de clase base, el método de clase base también debe tener el mismo **LinkDemand** para el método invalidado para que sea efectivo. Es posible que el código malintencionado pueda convertirse al tipo base y llamar al método de clase base. También tenga en cuenta que las peticiones de vínculo puede agregarse implícitamente a los ensamblados que no tienen el atributo de nivel de ensamblado <xref:System.Security.AllowPartiallyTrustedCallersAttribute>.  
  
 Es conveniente proteger las implementaciones de método con peticiones de vínculo cuando los métodos de interfaz también tienen peticiones de vínculo. Tenga en cuenta los siguientes aspectos sobre el uso de las peticiones de vínculo con interfaces:  
  
- Si coloca una **LinkDemand** en un método público de una clase que implementa un método de interfaz, **LinkDemand** no se aplicará si después convierte en la interfaz y llama al método. En este caso, dado que se ha vinculado a la interfaz, solo se respeta el **LinkDemand** de la interfaz.  
  
 Revise los elementos siguientes para comprobar si hay problemas de seguridad:  
  
- Peticiones de vínculo explícitas en métodos de interfaz. Asegúrese de que estas peticiones de vínculo ofrecen la protección esperada. Determine si el código malintencionado puede usar una conversión para evitar las peticiones de vínculo, como se describió anteriormente.  
  
- Métodos virtuales con peticiones de vínculo aplicadas.  
  
- Tipos y las interfaces que implementan. Deben usar las peticiones de vínculo de manera coherente.  
  
## <a name="see-also"></a>Consulte también

- [Instrucciones de codificación segura](../../standard/security/secure-coding-guidelines.md)
