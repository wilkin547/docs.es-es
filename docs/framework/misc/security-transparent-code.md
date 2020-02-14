---
title: Código transparente en seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- transparent code
- security-transparent code
ms.assetid: 4f3dd841-82f7-4659-aab0-6d2db2166c65
ms.openlocfilehash: ca251ec3084d40269b107e7bd8bef708e8d49622
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215829"
---
# <a name="security-transparent-code"></a>Código transparente en seguridad

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

En la seguridad participan tres partes interrelacionadas: espacio aislado, permisos y cumplimiento. Espacio aislado se refiere a la práctica de crear dominios aislados, donde una parte del código se trata como un código de plena confianza y la otra se restringe al conjunto de permisos concedidos al espacio aislado. El código de aplicación que se ejecuta en el conjunto de permisos del espacio aislado se considera transparente, es decir, no puede realizar operaciones que puedan afectar a la seguridad. El conjunto de permisos del espacio aislado se determina mediante evidencia (clase <xref:System.Security.Policy.Evidence>). La evidencia identifica los permisos específicos que los espacios aislados requieren y los tipos de espacios aislados que se pueden crear. El cumplimiento se refiere a permitir que el código transparente tan solo se ejecute dentro su conjunto de permisos.

> [!IMPORTANT]
> La directiva de seguridad era un elemento clave en las versiones anteriores de .NET Framework, A partir de la .NET Framework 4, la Directiva de seguridad está obsoleta. La eliminación de la directiva de seguridad es independiente de la transparencia de seguridad. Para obtener información sobre los efectos de este cambio, vea [compatibilidad y migración](code-access-security-policy-compatibility-and-migration.md)de la Directiva de seguridad de acceso del código.

## <a name="purpose-of-the-transparency-model"></a>Propósito del modelo de transparencia

La transparencia es un mecanismo de cumplimiento que separa el código que se ejecuta como parte de la aplicación del código que se ejecuta como parte de la infraestructura. La transparencia dibuja una barrera entre el código que puede realizar acciones con privilegios (código crítico), como llamar a código nativo, y el código sin esa capacidad (código transparente). El código transparente puede ejecutar comandos dentro de los límites del conjunto de permisos en el que opera, pero no puede ejecutar ni contener código crítico, ni tampoco derivar de él.

El objetivo principal del cumplimiento de la transparencia es proporcionar un mecanismo sencillo y eficaz para aislar grupos diferentes de código en función de los privilegios. En el contexto del modelo de espacio aislado, estos grupos de privilegios son de plena confianza (es decir, no restringidos) o de confianza parcial (es decir, restringidos al conjunto de permisos concedido al espacio aislado).

> [!IMPORTANT]
> El modelo de transparencia trasciende a la seguridad de acceso del código. El compilador Just-In-Time hace cumplir la transparencia, la cual permanece en vigor independientemente del conjunto de permisos concedidos a un ensamblado, incluida la plena confianza.

La transparencia se introdujo en .NET Framework 2.0 para simplificar el modelo de seguridad y para facilitar la escritura e implementación de aplicaciones y bibliotecas seguras. El código transparente también se usa en Microsoft Silverlight a fin de simplificar el desarrollo de aplicaciones de confianza parcial.

> [!NOTE]
> Al desarrollar una aplicación de confianza parcial, hay que tener en cuenta los requisitos de permisos para los hosts de destino. Si se desarrolla una aplicación que usa recursos no permitidos por algunos hosts, la aplicación se compilará sin problemas, pero producirá error cuando se cargue en el entorno hospedado. Si ha desarrollado su aplicación con Visual Studio, puede habilitar la depuración en confianza parcial o en un conjunto de permisos restringidos desde el entorno de desarrollo. Para obtener más información, consulta [Cómo: Depurar una aplicación ClickOnce con permisos restringidos](/visualstudio/deployment/how-to-debug-a-clickonce-application-with-restricted-permissions). La característica Calcular permisos proporcionada para aplicaciones ClickOnce también está disponible para cualquier aplicación de confianza parcial.

## <a name="specifying-the-transparency-level"></a>Especificar el nivel de transparencia

El atributo <xref:System.Security.SecurityRulesAttribute> de nivel de ensamblado selecciona de forma explícita las reglas <xref:System.Security.SecurityRuleSet> que seguirá el ensamblado. Las reglas se organizan en un sistema de niveles numéricos en el que los niveles superiores implican un cumplimiento más estricto de reglas de seguridad.

Los niveles son los siguientes:

- Nivel 2 (<xref:System.Security.SecurityRuleSet.Level2>): las reglas de transparencia de .NET Framework 4.

- Nivel 1 (<xref:System.Security.SecurityRuleSet.Level1>): las reglas de transparencia de .NET Framework 2.0.

La diferencia principal entre los dos niveles de transparencia es que el nivel 1 no exige el cumplimiento de las reglas de transparencia en las llamadas hechas desde fuera del ensamblado y se usa únicamente por razones de compatibilidad.

> [!IMPORTANT]
> Debe especificar la transparencia de nivel 1 solo para la compatibilidad; es decir, especifique el nivel 1 únicamente para el código que se desarrolló con .NET Framework 3.5 o versiones anteriores que usa el atributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute> o que no usa el modelo de transparencia. Por ejemplo, use la transparencia de nivel 1 para ensamblados de .NET Framework 2.0 que permiten llamadas de llamadores de confianza parcial (APTCA). Para el código que se desarrolla para el .NET Framework 4, use siempre la transparencia de nivel 2.

### <a name="level-2-transparency"></a>Transparencia de nivel 2

La transparencia de nivel 2 se presentó en el .NET Framework 4. Los tres principios de este modelo son código transparente, código crítico para la seguridad y disponible desde código transparente, y código crítico para la seguridad.

- El código transparente, independientemente de los permisos que se le conceden (incluida la plena confianza), solo puede llamar a otro código transparente o a código crítico para la seguridad y disponible desde código transparente. Si el código es de confianza parcial, solo puede realizar acciones permitidas por el conjunto de permisos del dominio. El código transparente no puede hacer lo siguiente:

  - Realizar una operación <xref:System.Security.CodeAccessPermission.Assert%2A> o una elevación de privilegios.

  - Contener código no seguro o no comprobable.

  - Llamar directamente a código crítico.

  - Llamar a código nativo o a código que tiene el atributo <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>.

  - Llamar a un miembro que está protegido por <xref:System.Security.Permissions.SecurityAction.LinkDemand>.

  - Heredar de tipos críticos.

    Además, los métodos transparentes no pueden invalidar métodos virtuales críticos o implementar métodos de interfaz críticos.

- El código crítico para la seguridad y disponible desde código transparente es de plena confianza, pero puede llamarlo el código transparente y exhibe un área expuesta limitada de código de plena confianza. Las comprobaciones de corrección y seguridad se producen en código crítico para la seguridad.

- El código crítico para la seguridad puede llamar a cualquier código y es de plena confianza, pero no se puede llamar mediante código transparente.

### <a name="level-1-transparency"></a>Transparencia de nivel 1

El modelo de transparencia de nivel 1 se introdujo en .NET Framework 2.0 para permitir a los desarrolladores reducir la cantidad de código que está sujeto a una auditoría de seguridad. Aunque la transparencia de nivel 1 se puso a disposición del público en la versión 2.0, se usaba fundamentalmente de forma interna en Microsoft con fines de auditoría de seguridad. Mediante las anotaciones, los desarrolladores pueden declarar qué tipos y miembros pueden realizar elevaciones de seguridad y otras acciones de confianza (críticos para la seguridad) y cuáles no (transparentes en seguridad). El código que se identifica como transparente no requiere un alto grado de auditoría de seguridad. La transparencia de nivel 1 indica que el cumplimiento de la transparencia se limita a dentro del ensamblado. En otras palabras, los tipos o miembros públicos que se identifican como críticos para la seguridad lo son únicamente dentro del ensamblado. Si desea exigir el cumplimiento de la seguridad en estos tipos y miembros cuando se les llama desde fuera del ensamblado, use peticiones de vínculo de plena confianza. Si no lo hace, los miembros y los tipos críticos para la seguridad y públicamente visibles se tratarán como críticos para la seguridad y disponibles desde código transparente, y podrán ser llamados por código de confianza parcial desde fuera del ensamblado.

El modelo de transparencia de nivel 1 tiene las siguientes limitaciones:

- Los tipos y miembros críticos para la seguridad que son públicos son accesibles desde código transparente en seguridad.

- Las anotaciones de transparencia se aplican solo dentro de un ensamblado.

- Los tipos y miembros críticos para la seguridad deben usar peticiones de vínculo para exigir el cumplimiento de la seguridad en las llamadas desde fuera del ensamblado.

- No se aplican las reglas de herencia.

- Existe la posibilidad de que el código transparente sea perjudicial si se ejecuta con plena confianza.

## <a name="transparency-enforcement"></a>Cumplimiento de la transparencia

Las reglas de transparencia no se aplican hasta que se calcula la transparencia. En ese momento, se genera una <xref:System.InvalidOperationException> si se infringe una regla de transparencia. El momento en que se calcula la transparencia depende de varios factores y no se puede predecir. Se calcula lo más tarde posible. En el .NET Framework 4, el cálculo de transparencia de nivel de ensamblado se produce antes que en el .NET Framework 2,0. La única garantía es que el cálculo de transparencia se producirá cuando sea necesario. Esto es similar a cómo el compilador Just-In-Time (JIT) puede cambiar el punto cuando se compila un método y se detectan errores en ese método. El cálculo de transparencia es invisible si el código no tiene errores de transparencia.

## <a name="see-also"></a>Consulte también

- [Código transparente en seguridad, nivel 1](security-transparent-code-level-1.md)
- [Código transparente en seguridad, nivel 2](security-transparent-code-level-2.md)
