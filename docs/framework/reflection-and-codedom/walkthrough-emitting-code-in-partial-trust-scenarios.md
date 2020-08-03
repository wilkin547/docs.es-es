---
title: 'Tutorial: Emisión de código en escenarios que no son de plena confianza'
description: Vea cómo emitir código en escenarios que no son de plena confianza. La emisión de reflexión usa las mismas API, pero algunas características requieren permisos especiales en código de confianza parcial.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- reflection emit, anonymously hosted dynamic methods
- partial trust, reflection
- partial trust, emitting dynamic methods
- reflection emit, partial trust scenarios
- anonymously hosted dynamic methods [.NET Framework]
- emitting dynamic assemblies,partial trust scenarios
- reflection emit, dynamic methods
- dynamic methods
ms.assetid: c45be261-2a9d-4c4e-9bd6-27f0931b7d25
ms.openlocfilehash: 70adb3ce67b45459b18741948092a912f6173731
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865195"
---
# <a name="walkthrough-emitting-code-in-partial-trust-scenarios"></a>Tutorial: Emisión de código en escenarios que no son de plena confianza

La emisión de reflexión usa el mismo conjunto de API con confianza completa o parcial, pero algunas características requieren permisos especiales en entornos de confianza parcial. Además, la emisión de reflexión tiene una característica, los métodos dinámicos hospedados de forma anónima, diseñada para su uso en entornos de confianza parcial y por ensamblados transparentes en seguridad.

> [!NOTE]
> Antes de .NET Framework 3.5, la emisión de código requería <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit?displayProperty=nameWithType>. Este permiso está incluido de forma predeterminada en los conjuntos de permisos con nombre `FullTrust` e `Intranet`, pero no en el conjunto de permisos `Internet`. Por tanto, se podría usar una biblioteca de confianza parcial solo si tuviera el atributo <xref:System.Security.SecurityCriticalAttribute> y también se ejecutara un método <xref:System.Security.PermissionSet.Assert%2A> para <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>. Estas bibliotecas requieren una revisión cuidadosa de la seguridad porque los errores de codificación pueden provocar vulnerabilidades de seguridad. .NET Framework 3.5 permite emitir código en escenarios de confianza parcial sin emitir ninguna petición de seguridad, porque la generación de código no es en sí una operación que requiera privilegios. Es decir, el código generado no tiene más permisos que el ensamblado que lo emite. Esto permite que las bibliotecas que emiten código sean transparentes en seguridad y quita la necesidad de validar <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>, de manera que escribir una biblioteca segura no requiere este tipo de revisión exhaustiva de la seguridad.

En este tutorial se muestran las tareas siguientes:

- [Preparar un espacio aislado sencillo para probar el código de confianza parcial](#Setting_up).

  > [!IMPORTANT]
  > Ésta es una manera sencilla de experimentar con código con confianza parcial. Para ejecutar código procedente de ubicaciones que no son de confianza, vea [Cómo: Ejecutar código de confianza parcial en un espacio aislado](../misc/how-to-run-partially-trusted-code-in-a-sandbox.md).

- [Ejecutar código en dominios de aplicación de confianza parcial](#Running_code).

- [Usar métodos dinámicos hospedados de forma anónima para emitir y ejecutar el código en entornos de confianza parcial](#Using_methods).

Para obtener más información sobre cómo emitir código en escenarios de confianza parcial, vea [Problemas de seguridad en la emisión de la reflexión](security-issues-in-reflection-emit.md).

Para obtener una lista completa del código mostrado en estos procedimientos, vea la [sección Ejemplo](#Example) al final de este tutorial.

<a name="Setting_up"></a>

## <a name="setting-up-partially-trusted-locations"></a>Preparar las ubicaciones de confianza parcial

En los dos procedimientos siguientes se muestra cómo preparar las ubicaciones desde las que puede probar el código con confianza parcial.

- En el primer procedimiento se muestra cómo crear un dominio de aplicación en un espacio aislado en el que el código tiene permisos de Internet.

- En el segundo procedimiento se muestra cómo agregar <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> a un dominio de aplicación de confianza parcial, y de este modo habilitar a los ensamblados con una confianza igual o menor para el acceso a los datos privados.

### <a name="creating-sandboxed-application-domains"></a>Crear dominios de aplicación en recintos de seguridad

Para crear un dominio de aplicación en el que los ensamblados se ejecuten con confianza parcial, debe especificar el conjunto de permisos que se va a conceder a los ensamblados mediante la sobrecarga del método <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> para crear el dominio de aplicación. La manera más fácil de especificar el conjunto de permisos concedidos es recuperar un conjunto de permisos con nombre de la directiva de seguridad.

En el procedimiento siguiente se crea un dominio de aplicación en un espacio aislado que ejecuta el código de confianza parcial, para probar los escenarios en los que el código emitido sólo puede tener acceso a los miembros públicos de tipos públicos. En un procedimiento posterior se muestra cómo agregar <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess> para probar los escenarios en los que el código emitido puede tener acceso a los tipos y miembros no públicos de los ensamblados con permisos iguales o menores.

#### <a name="to-create-an-application-domain-with-partial-trust"></a>Para crear un dominio de aplicación con confianza parcial

1. Cree un conjunto de permisos que se concedan a los ensamblados del dominio de aplicación en un espacio aislado. En este caso, se utiliza el conjunto de permisos de la zona de Internet.

    [!code-csharp[HowToEmitCodeInPartialTrust#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#2)]
    [!code-vb[HowToEmitCodeInPartialTrust#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#2)]

2. Cree un objeto <xref:System.AppDomainSetup> para inicializar el dominio de aplicación con una ruta de aplicación.

    > [!IMPORTANT]
    > Para simplificar, en este ejemplo de código se usa la carpeta actual. Para ejecutar código que procede de Internet, use una carpeta independiente para el código que no es de confianza, como se describe en [Cómo: Ejecutar código de confianza parcial en un espacio aislado](../misc/how-to-run-partially-trusted-code-in-a-sandbox.md).

    [!code-csharp[HowToEmitCodeInPartialTrust#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#3)]
    [!code-vb[HowToEmitCodeInPartialTrust#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#3)]

3. Cree el dominio de aplicación, especificando la información sobre configuración del dominio de aplicación y el conjunto de permisos concedidos para todos los ensamblados que se ejecutan en el dominio de aplicación.

    [!code-csharp[HowToEmitCodeInPartialTrust#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#5)]
    [!code-vb[HowToEmitCodeInPartialTrust#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#5)]

    El último parámetro de la sobrecarga del método <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> permite especificar un conjunto de ensamblados a los que se concederá plena confianza, en lugar del conjunto de permisos concedidos del dominio de aplicación. No es necesario especificar los ensamblados de .NET Framework que la aplicación usa, porque esos ensamblados están en la caché global de ensamblados. Los ensamblados que están en la caché global de ensamblados siempre son de plena confianza. Puede usar este parámetro para especificar ensamblados con nombre seguro que no están en la caché global de ensamblados.

### <a name="adding-restrictedmemberaccess-to-sandboxed-domains"></a>Agregar RestrictedMemberAccess a dominios en recintos de seguridad

Las aplicaciones host pueden permitir que los métodos dinámicos hospedados de forma anónima tengan acceso a los datos privados de ensamblados con niveles de confianza igual o menor que el nivel de confianza del ensamblado que emite el código. Para habilitar esta capacidad restringida para omitir las comprobaciones de visibilidad Just-In-Time (JIT), la aplicación host agrega un objeto <xref:System.Security.Permissions.ReflectionPermission> con el marcador <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> (RMA) al conjunto de permisos concedidos.

Por ejemplo, un host podría conceder a aplicaciones de Internet permisos de Internet más RMA, de manera que una aplicación de Internet pueda emitir código que tiene acceso a los datos privados de sus propios ensamblados. Debido a que el acceso se limita a los ensamblados con una confianza igual o menor, una aplicación de Internet no puede acceder a los miembros de ensamblados de plena confianza, como los ensamblados de .NET Framework.

> [!NOTE]
> Para evitar la elevación de privilegios, la información de pila del ensamblado emisor se incluye al construir los métodos dinámicos hospedados de forma anónima. Cuando se invoca el método, se comprueba la información de la pila. Así, un método dinámico hospedado de forma anónima que se invoca desde código de plena confianza seguirá limitado al nivel de confianza del ensamblado emisor.

#### <a name="to-create-an-application-domain-with-partial-trust-plus-rma"></a>Para crear un dominio de aplicación con confianza parcial más RMA

1. Cree un nuevo objeto <xref:System.Security.Permissions.ReflectionPermission> con la marca (RMA) <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess> y use el método <xref:System.Security.PermissionSet.SetPermission%2A?displayProperty=nameWithType> para agregar el permiso al conjunto de permisos concedidos.

    [!code-csharp[HowToEmitCodeInPartialTrust#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#7)]
    [!code-vb[HowToEmitCodeInPartialTrust#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#7)]

    El método <xref:System.Security.PermissionSet.AddPermission%2A> agrega el permiso al conjunto de permisos concedidos si aún no está incluido. Si el permiso ya está incluido en el conjunto de permisos concedidos, los marcadores especificados se agregan al permiso existente.

    > [!NOTE]
    > RMA es una característica de los métodos dinámicos hospedados de forma anónima. Cuando los métodos dinámicos normales omiten las comprobaciones de visibilidad JIT, el código emitido requiere plena confianza.

2. Cree el dominio de aplicación y especifique la información sobre configuración del dominio de aplicación y el conjunto de permisos concedidos.

    [!code-csharp[HowToEmitCodeInPartialTrust#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#8)]
    [!code-vb[HowToEmitCodeInPartialTrust#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#8)]

<a name="Running_code"></a>

## <a name="running-code-in-sandboxed-application-domains"></a>Ejecutar código en dominios de aplicación en un espacio aislado

En el procedimiento siguiente se explica cómo definir una clase mediante métodos que se pueden ejecutar en un dominio de aplicación, cómo crear una instancia de la clase en el dominio y cómo ejecutar sus métodos.

#### <a name="to-define-and-execute-a-method-in-an-application-domain"></a>Para definir y ejecutar un método en un dominio de aplicación

1. Defina una clase que se derive de <xref:System.MarshalByRefObject>. Esto permite crear instancias de la clase en otros dominios de aplicación y realizar llamadas a métodos en los límites del dominio de aplicación. En este ejemplo, la clase se denomina `Worker`.

    [!code-csharp[HowToEmitCodeInPartialTrust#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#10)]
    [!code-vb[HowToEmitCodeInPartialTrust#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#10)]

2. Defina un método público que contenga el código que desea ejecutar. En este ejemplo, el código emite un método dinámico simple, crea un delegado para ejecutar el método e invoca al delegado.

    [!code-csharp[HowToEmitCodeInPartialTrust#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#11)]
    [!code-vb[HowToEmitCodeInPartialTrust#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#11)]

3. En el programa principal, obtenga el nombre para mostrar del ensamblado. Este nombre se usa al crear instancias de la clase `Worker` en el dominio de aplicación en un espacio aislado.

    [!code-csharp[HowToEmitCodeInPartialTrust#14](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#14)]
    [!code-vb[HowToEmitCodeInPartialTrust#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#14)]

4. En el programa principal, cree un dominio de aplicación en un espacio aislado, como se describe en [el primer procedimiento](#Setting_up) de este tutorial. No es necesario agregar ningún permiso al conjunto de permisos `Internet`, porque el método `SimpleEmitDemo` sólo usa métodos públicos.

5. En el programa principal, cree una instancia de la clase `Worker` en el dominio de aplicación en un espacio aislado.

    [!code-csharp[HowToEmitCodeInPartialTrust#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#12)]
    [!code-vb[HowToEmitCodeInPartialTrust#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#12)]

    El método <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> crea el objeto en el dominio de aplicación de destino y devuelve un proxy que se puede usar para llamar a las propiedades y métodos del objeto.

    > [!NOTE]
    > Si usa este código en Visual Studio, debe cambiar el nombre de la clase para que incluya el espacio de nombres. De forma predeterminada, el espacio de nombres es el nombre del proyecto. Por ejemplo, si el proyecto es "PartialTrust", el nombre de clase debe ser "PartialTrust.Worker".

6. Agregue código para llamar al método `SimpleEmitDemo`. Se calculan las referencias de la llamada en el límite del dominio de aplicación y el código se ejecuta en el dominio de aplicación en un espacio aislado.

    [!code-csharp[HowToEmitCodeInPartialTrust#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#13)]
    [!code-vb[HowToEmitCodeInPartialTrust#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#13)]

<a name="Using_methods"></a>

## <a name="using-anonymously-hosted-dynamic-methods"></a>Usar métodos dinámicos hospedados de forma anónima

Los métodos dinámicos hospedados de forma anónima están asociados a un ensamblado transparente proporcionado por el sistema. Por consiguiente, el código que contienen es transparente. Los métodos dinámicos normales, por otro lado, deben estar asociados a un módulo existente (directamente especificados o deducidos de un tipo asociado) y toman el nivel de seguridad de ese módulo.

> [!NOTE]
> La única manera de asociar un método dinámico al ensamblado que proporciona hospedaje anónimo es usar los constructores que se describen en el procedimiento siguiente. No puede especificar explícitamente un módulo en el ensamblado hospedado de forma anónima.

Los métodos dinámicos normales tienen acceso a los miembros internos del módulo al que están asociados o a los miembros privados del tipo al que están asociados. Debido a que los métodos dinámicos de hospedaje anónimo están aislados del resto del código, no tienen acceso a los datos privados. Sin embargo, tienen una capacidad restringida para omitir las comprobaciones de visibilidad JIT para obtener acceso a los datos privados. Esta capacidad se limita a los ensamblados que tienen un nivel de confianza igual o menor que el nivel de confianza del ensamblado que emite el código.

Para evitar la elevación de privilegios, la información de pila del ensamblado emisor se incluye al construir los métodos dinámicos hospedados de forma anónima. Cuando se invoca el método, se comprueba la información de la pila. Un método dinámico hospedado de forma anónima que se invoca desde código de plena confianza seguirá limitado al nivel de confianza del ensamblado que lo emitió.

#### <a name="to-use-anonymously-hosted-dynamic-methods"></a>Para usar métodos dinámicos hospedados de forma anónima

- Cree un método dinámico hospedado de forma anónima mediante un constructor que no especifique ningún módulo o tipo asociado.

  [!code-csharp[HowToEmitCodeInPartialTrust#15](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#15)]
  [!code-vb[HowToEmitCodeInPartialTrust#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#15)]

  Si un método dinámico hospedado de forma anónima sólo usa tipos y métodos públicos, no necesita acceso restringido a los miembros y no tiene que omitir las comprobaciones de visibilidad JIT.

  No son necesarios permisos especiales para emitir un método dinámico, pero el código emitido requiere los permisos exigidos por los tipos y métodos que use. Por ejemplo, si el código emitido llama a un método que tiene acceso a un archivo, requiere <xref:System.Security.Permissions.FileIOPermission>. Si el nivel de confianza no incluye ese permiso, se produce una excepción de seguridad al ejecutar el código emitido. El código mostrado aquí emite un método dinámico que sólo usa el método <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>. Por consiguiente, el código se puede ejecutar desde ubicaciones de confianza parcial.

- Opcionalmente, para crear un método dinámico de host anónimo con capacidad restringida para omitir las comprobaciones de visibilidad JIT, puede usar el constructor <xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%2CSystem.Boolean%29> y especificar `true` para el parámetro `restrictedSkipVisibility`.

  [!code-csharp[HowToEmitCodeInPartialTrust#16](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#16)]
  [!code-vb[HowToEmitCodeInPartialTrust#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#16)]

  La restricción es que el método dinámico hospedado de forma anónima sólo puede tener acceso a los datos privados de ensamblados con niveles de confianza iguales o menores que el nivel de confianza del ensamblado emisor. Por ejemplo, si el método dinámico se ejecuta con confianza en Internet, puede acceder a los datos privados de otros ensamblados que también se ejecutan con confianza en Internet, pero no puede acceder a los datos privados de ensamblados de .NET Framework. Los ensamblados de .NET Framework están instalados en la caché global de ensamblados y son siempre de plena confianza.

  Los métodos dinámicos hospedados de forma anónima pueden usar esta capacidad restringida para omitir las comprobaciones de visibilidad JIT sólo si la aplicación host concede <xref:System.Security.Permissions.ReflectionPermission> con el marcador <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>. La petición de este permiso se realiza al invocar el método.

  > [!NOTE]
  > La información de pila de llamadas del ensamblado emisor se incluye al construir el método dinámico. Por consiguiente, se realiza una petición de los permisos del ensamblado emisor, no del ensamblado que invoca el método. Así se evita que el código emitido se ejecute con permisos elevados.

  El [ejemplo de código completo](#Example) al final de este tutorial muestra el uso y las limitaciones de acceso a miembros restringidos. Su clase `Worker` incluye un método que puede crear métodos dinámicos hospedados de forma anónima con o sin la capacidad restringida de omitir las comprobaciones de visibilidad y el ejemplo muestra el resultado de ejecutar este método en dominios de aplicación que tienen niveles de confianza diferentes.

  > [!NOTE]
  > La capacidad restringida de omitir las comprobaciones de visibilidad es una característica de los métodos dinámicos hospedados de forma anónima. Cuando los métodos dinámicos normales omiten las comprobaciones de visibilidad JIT, se les debe otorgar plena confianza.

<a name="Example"></a>

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción

En el ejemplo de código siguiente se muestra cómo se utiliza el marcador <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess> para permitir que los métodos dinámicos hospedados de forma anónima omitan las comprobaciones de visibilidad JIT, pero sólo cuando el miembro de destino tiene un nivel de confianza igual o menor que el ensamblado que emite el código.

El ejemplo define una clase `Worker` cuyas referencias se pueden calcular en los límites del dominio de aplicación. La clase tiene dos sobrecargas de método `AccessPrivateMethod` que emiten y ejecutan métodos dinámicos. La primera sobrecarga emite un método dinámico que llama al método privado `PrivateMethod` de la clase `Worker` y puede emitir el método dinámico con o sin comprobaciones de visibilidad JIT. La segunda sobrecarga emite un método dinámico que tiene acceso a una propiedad `internal` (propiedad `Friend` en Visual Basic) de la clase <xref:System.String>.

El ejemplo usa un método del asistente para crear un conjunto de permisos concedidos limitado a los permisos de `Internet` y crea un dominio de aplicación mediante la sobrecarga del método <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> para especificar que todo el código que se ejecute en el dominio usa este conjunto de permisos concedidos. En el ejemplo se crea una instancia de la clase `Worker` en el dominio de aplicación y se ejecuta el método `AccessPrivateMethod` dos veces.

- La primera vez que se ejecuta el método `AccessPrivateMethod`, se exigen las comprobaciones de visibilidad JIT. Se producirá un error en el método dinámico cuando se invoque, porque las comprobaciones de visibilidad JIT le impedirán el acceso al método privado.

- La segunda vez que se ejecuta el método `AccessPrivateMethod`, se omiten las comprobaciones de visibilidad JIT. Se producirá un error en el método dinámico al compilarse, porque el conjunto de permisos concedidos `Internet` no concede permisos suficientes para omitir las comprobaciones de visibilidad.

El ejemplo siguiente agrega <xref:System.Security.Permissions.ReflectionPermission> con <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> al conjunto de permisos concedidos. A continuación, en el ejemplo se crea un segundo dominio y se especifica que todo el código que se ejecute en el dominio tenga los permisos del nuevo conjunto de permisos concedidos. En el ejemplo se crea una instancia de la clase `Worker` en el nuevo dominio de aplicación y se ejecutan las dos sobrecargas del método `AccessPrivateMethod`.

- Se ejecuta la primera sobrecarga del método `AccessPrivateMethod` y se omiten las comprobaciones de visibilidad JIT. El método dinámico se compila y se ejecuta correctamente, porque el ensamblado que emite el código es igual que el ensamblado que contiene el método privado. Por consiguiente, los niveles de confianza son iguales. Si la aplicación que contiene la clase `Worker` tuviera varios ensamblados, el mismo proceso sería correcto para cualquiera de esos ensamblados, porque todos tendrían el mismo nivel de confianza.

- Se ejecuta la segunda sobrecarga del método `AccessPrivateMethod` y, de nuevo, se omiten las comprobaciones de visibilidad JIT. Esta vez, se produce un error en el método dinámico al compilarse porque intenta tener acceso a la propiedad `internal` `FirstChar` de la clase <xref:System.String>. El ensamblado que contiene la clase <xref:System.String> es de plena confianza. Por consiguiente, está en un nivel de confianza superior al del ensamblado que emite el código.

Esta comparación muestra cómo <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> habilita al código de confianza parcial para omitir las comprobaciones de visibilidad de otro código de confianza parcial sin poner en peligro la seguridad del código de confianza.

### <a name="code"></a>Código

[!code-csharp[HowToEmitCodeInPartialTrust#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#1)]
[!code-vb[HowToEmitCodeInPartialTrust#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#1)]

## <a name="compiling-the-code"></a>Compilar el código

- Si compila este código de ejemplo en Visual Studio, debe cambiar el nombre de la clase para que incluya el espacio de nombres al pasarla al método <xref:System.AppDomain.CreateInstanceAndUnwrap%2A>. De forma predeterminada, el espacio de nombres es el nombre del proyecto. Por ejemplo, si el proyecto es "PartialTrust", el nombre de clase debe ser "PartialTrust.Worker".

## <a name="see-also"></a>Vea también

- [Problemas de seguridad en la emisión de la reflexión](security-issues-in-reflection-emit.md)
- [Cómo: Ejecutar código de confianza parcial en un espacio aislado](../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
