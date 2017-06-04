---
title: "Securing Wrapper Code | Microsoft Docs"
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
  - "security [.NET Framework], wrapper code"
  - "wrapper code, securing"
  - "secure coding, wrapper code"
  - "code security, wrapper code"
ms.assetid: 1df6c516-5bba-48bd-b450-1070e04b7389
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Securing Wrapper Code
El código de contenedor, especialmente cuando el contenedor tiene mayor confianza que el código que lo usa, puede descubrir un conjunto único de vulnerabilidades de seguridad. Todo lo hecho en nombre de un llamador, cuyos permisos limitados no se incluyen en la comprobación de seguridad adecuada, es una vulnerabilidad potencial que puede ser aprovechada.  
  
 No habilite nunca nada a través del contenedor que el llamador no pueda hacer él mismo. Esto es especialmente peligroso cuando se realiza una acción que implica una comprobación de seguridad limitada, en lugar de una petición de recorrido de pila completo. Si hay comprobaciones de nivel único implicadas, la interposición de código de contenedor entre el llamador real y el elemento de la API en cuestión puede hacer fácilmente que la comprobación de seguridad tenga éxito cuando no debería tenerlo, con el consiguiente debilitamiento de la seguridad.  
  
> [!CAUTION]
>  Seguridad de acceso del código y código de confianza parcial  
>   
>  .NET Framework proporciona seguridad de acceso del código \(CAS\), que es un mecanismo para el cumplimiento de los distintos niveles de confianza en diferentes códigos que se ejecutan en la misma aplicación.  La seguridad de acceso del código en .NET Framework no debe usarse como límite de seguridad para código de confianza parcial, especialmente si se trata de código de origen desconocido. Le aconsejamos que no cargue ni ejecute código de orígenes desconocidos sin contar con medidas de seguridad alternativas.  
>   
>  Esta directiva se aplica a todas las versiones de .NET Framework, pero no se aplica a la versión de .NET Framework incluida en Silverlight.  
  
## Delegados  
 La seguridad de los delegados difiere entre las versiones de .NET Framework.  En esta sección se describe el comportamiento de los distintos delegados y las consideraciones de seguridad asociadas.  
  
### En las versiones 1.0 y 1.1 de .NET Framework  
 Las versiones 1.0 y 1.1 de .NET Framework llevan a cabo las siguientes acciones de seguridad frente a un creador de delegado y un llamador de delegado.  
  
-   Cuando se crea un delegado, las peticiones de vínculo de seguridad en el método de destino del delegado se realizan en el conjunto de permisos del creador del delegado.  El incumplimiento de la acción de seguridad produce un <xref:System.Security.SecurityException>.  
  
-   Cuando se invoca el delegado, se realiza cualquier petición de seguridad existente en el llamador del delegado.  
  
 Siempre que su código tome un <xref:System.Delegate> de un código de menor confianza que pueda llamarlo, asegúrese de que no habilita al código de menor confianza para que aumente sus permisos. Si toma un delegado y lo usa más adelante, el código que creó el delegado no está en la pila de llamadas y sus permisos no se probarán si el código que está en el delegado o bajo el delegado intenta una operación protegida. Si su código y el código del llamador tienen privilegios más elevados que el creador, el creador puede organizar la ruta de la llamada sin formar parte de la pila de llamadas.  
  
### En la versión 2.0 y posteriores de .NET Framework  
 A diferencia de las versiones anteriores, la versión 2.0 de .NET Framework realiza una acción de seguridad en el creador del delegado en el momento en que el delegado se crea y se llama.  
  
-   Cuando se crea un delegado, las peticiones de vínculo de seguridad en el método de destino del delegado se realizan en el conjunto de permisos del creador del delegado.  El incumplimiento de la acción de seguridad produce un <xref:System.Security.SecurityException>.  
  
-   El conjunto de permisos del creador del delegado también se captura durante la creación del delegado y se almacena con dicho delegado.  
  
-   Cuando se invoca el delegado, el conjunto de permisos capturado del creador del delegado se evalúa en primer lugar frente a las peticiones en el contexto actual si el creador del delegado y el llamador pertenecen a distintos ensamblados.  A continuación, se realizan todas las peticiones de seguridad existentes en el llamador del delegado.  
  
## Peticiones de vínculo y contenedores  
 Se ha reforzado un caso especial de protección con peticiones de vínculo en la infraestructura de seguridad, pero sigue siendo una fuente de posibles vulnerabilidades en el código.  
  
 Si un código de plena confianza llama a una propiedad, evento o método protegido mediante un [LinkDemand](../../../docs/framework/misc/link-demands.md), la llamada se realiza correctamente si se cumple la comprobación de permisos de **LinkDemand** para el llamador. Además, si el código de plena confianza expone una clase que toma el nombre de una propiedad y llama a su descriptor de acceso **get** mediante reflexión, esa llamada al descriptor de acceso **get** se realiza correctamente aunque el código de usuario no tenga el derecho de acceso a esta propiedad. Esto se debe a que **LinkDemand** comprueba únicamente el llamador inmediato, que es el código de plena confianza. Básicamente, el código de plena confianza realiza una llamada privilegiada en nombre del código de usuario sin comprobar si el código de usuario tiene derecho a hacer esa llamada.  
  
 Para intentar evitar esas carencias de seguridad, Common Language Runtime extiende la comprobación a una petición de recorrido de pila completo en las llamadas indirectas a los métodos, constructores, propiedades o eventos que estén protegidos por un **LinkDemand**. Esta protección conlleva algunos costos de rendimiento y cambia la semántica de la comprobación de seguridad; la petición de recorrido de pila completo puede provocar errores que no se producirían en la comprobación rápida de un nivel.  
  
> [!NOTE]
>  En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], el código de confianza parcial se ha redefinido como código transparente. El modelo de transparencia dibuja una barrera entre el código que puede realizar acciones con privilegios \(código crítico\), como llamar a código nativo, y el código sin esa capacidad \(código transparente\). La transparencia reemplaza el uso de <xref:System.Security.Permissions.SecurityAction> de plena confianza para identificar código de plena confianza con el <xref:System.Security.SecurityCriticalAttribute>. Para más información sobre este y otros cambios, vea [Cambios de seguridad](../../../docs/framework/security/security-changes.md).  
  
## Contenedores de carga de ensamblados  
 Varios de los métodos usados para cargar código administrado, incluido <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>, cargan ensamblados con la evidencia del llamador. Si encapsula cualquiera de estos métodos, el sistema de seguridad podría usar, para cargar los ensamblados, el permiso concedido al código en lugar de los permisos del llamador para el contenedor. No permita que un código de menor confianza cargue código que tenga permisos superiores a los del llamador en el contenedor.  
  
 Cualquier código que tenga plena confianza o una confianza significativamente mayor que la de un posible llamador \(incluido un llamador con nivel de permisos de Internet\) podría debilitar la seguridad de esta manera. Si su código tiene un método público que toma una matriz de bytes y la pasa a **Assembly.Load**, con lo que se crea un ensamblado en nombre del llamador, se pueden producir fallos de seguridad.  
  
 Este problema se aplica a los siguientes elementos de la API:  
  
-   <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>  
  
## Demand versus LinkDemand  
 La seguridad declarativa ofrece dos tipos de comprobaciones de seguridad que son similares, pero que realizan comprobaciones muy diferentes. Debe entender ambas formas porque la opción incorrecta puede producir la pérdida de rendimiento o una seguridad débil.  
  
 La seguridad declarativa ofrece las siguientes comprobaciones de seguridad:  
  
-   <xref:System.Security.Permissions.SecurityAction> especifica el recorrido de pila de seguridad de acceso del código. Todos los llamadores de la pila deben tener el permiso o la identidad especificados para pasar.**Demand** se produce en cada llamada, ya que la pila puede contener distintos llamadores. Si llama a un método repetidas veces, esta comprobación de seguridad se realiza cada vez.**Demand** es una buena protección contra ataques por señuelo porque detectará el código no autorizado que intente salvar esta comprobación.  
  
-   [LinkDemand](../../../docs/framework/misc/link-demands.md) ocurre en tiempo de compilación Just\-In\-Time \(JIT\) y comprueba solo el llamador inmediato. Esta comprobación de seguridad no comprueba el llamador del llamador. Una vez que se supera esta comprobación, no hay ninguna seguridad adicional posterior independientemente de las veces que el llamador pueda llamar. Sin embargo, tampoco hay protección contra los ataques por señuelo. Con **LinkDemand**, cualquier código que pase la prueba y pueda hacer referencia al código supone una amenaza potencial para la seguridad al permitir que un código malintencionado pueda usar el código autorizado para realizar llamadas. Por lo tanto, no use **LinkDemand** a menos que se puedan evitar completamente todos los posibles puntos débiles.  
  
    > [!NOTE]
    >  En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], las peticiones de vínculo se han reemplazado por el atributo <xref:System.Security.SecurityCriticalAttribute> en ensamblados <xref:System.Security.SecurityRuleSet>.<xref:System.Security.SecurityCriticalAttribute> es equivalente a una petición de vínculo de plena confianza; sin embargo, también afecta a las reglas de herencia. Para más información sobre este cambio, vea [Security\-Transparent Code, Level 2](../../../docs/framework/misc/security-transparent-code-level-2.md).  
  
 Las precauciones adicionales necesarias para usar **LinkDemand** deben programarse por separado; el sistema de seguridad puede ayudar con la aplicación. Cualquier error abre una vulnerabilidad en la seguridad. Todo código autorizado que use su código debe hacerse responsable de implementar seguridad adicional mediante lo siguiente:  
  
-   Restringir el acceso del código de llamada a la clase o al ensamblado.  
  
-   Colocar en el código de llamada las mismas comprobaciones de seguridad que aparecen en el código al que se llama y obligar a sus llamadores a hacer lo mismo. Por ejemplo, si escribe código que llama a un método que está protegido con un elemento **LinkDemand** para el elemento <xref:System.Security.Permissions.SecurityPermission> con la marca <xref:System.Security.Permissions.SecurityPermissionFlag> especificada, el método debe generar también un elemento **LinkDemand** \(o **Demand**, que es más seguro\) para este permiso. La excepción es cuando su código usa el método protegido con **LinkDemand** de una forma limitada que usted considere segura porque el código ya contiene otros mecanismos de protección de seguridad \(como {i\>demands\<i}\). En este caso excepcional, el llamador es el responsable de debilitar la protección de seguridad en el código subyacente.  
  
-   Garantizar que los llamadores de su código no pueden engañar al código para que llame al código protegido en su nombre. En otras palabras, los llamadores no pueden forzar al código autorizado para pasar parámetros específicos al código protegido o para obtener resultados de él.  
  
### Interfaces y peticiones de vínculo  
 Si un método virtual, propiedad o evento con **LinkDemand** invalida un método de clase base, el método de clase base también debe tener el mismo **LinkDemand** para el método invalidado para que sea efectivo. Es posible que el código malintencionado pueda convertirse al tipo base y llamar al método de clase base. También tenga en cuenta que las peticiones de vínculo puede agregarse implícitamente a los ensamblados que no tienen el atributo de nivel de ensamblado <xref:System.Security.AllowPartiallyTrustedCallersAttribute>.  
  
 Es conveniente proteger las implementaciones de método con peticiones de vínculo cuando los métodos de interfaz también tienen peticiones de vínculo. Tenga en cuenta los siguientes aspectos sobre el uso de las peticiones de vínculo con interfaces:  
  
-   El atributo **AllowPartiallyTrustedCallersAttribute** también se aplica a las interfaces.  
  
-   Las peticiones de vínculo se pueden colocar en interfaces para evitar que determinadas interfaces sean usadas por código de confianza parcial, como cuando se usa el atributo **AllowPartiallyTrustedCallersAttribute** .  
  
-   Si tiene una interfaz definida en un ensamblado que no contiene el atributo **AllowPartiallyTrustedCallersAttribute** , puede implementar esa interfaz en una clase de confianza parcial.  
  
-   Si coloca un **LinkDemand** en un método público de una clase que implementa un método de interfaz, **LinkDemand** no se aplicará si, a continuación, se convierte en la interfaz y se llama al método. En este caso, dado que se ha vinculado con la interfaz, solo se cumplirá el **LinkDemand** en la interfaz.  
  
 Revise los elementos siguientes para comprobar si hay problemas de seguridad:  
  
-   Peticiones de vínculo explícitas en métodos de interfaz. Asegúrese de que estas peticiones de vínculo ofrecen la protección esperada. Determine si el código malintencionado puede usar una conversión para evitar las peticiones de vínculo, como se describió anteriormente.  
  
-   Métodos virtuales con peticiones de vínculo aplicadas.  
  
-   Tipos y las interfaces que implementan. Deben usar las peticiones de vínculo de manera coherente.  
  
## Vea también  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)