---
title: Consideraciones de migración
description: ¿Qué necesita saber un equipo para tomar la decisión correcta sobre si y cómo migrar de ASP.NET MVC a .NET Core?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: c669dc477469c92dfa3acda8209ba7a1fdea5ed5
ms.sourcegitcommit: b5d2290673e1c91260c9205202dd8b95fbab1a0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "106122864"
---
# <a name="migration-considerations"></a>Consideraciones de migración

Los equipos de preguntas más fundamentales deben responder cuando se trata de migrar sus aplicaciones a .NET Core, ¿deben migrar? En algunos casos, la mejor ruta de acceso hacia delante es permanecer en .NET Framework mediante ASP.NET MVC y/o API Web. En este capítulo se tienen en cuenta los motivos por los que el cambio a .NET Core tiene sentido. En el capítulo también se consideran escenarios y contrapuntos para permanecer en .NET Framework.

## <a name="is-migration-to-net-core-appropriate"></a>¿Es adecuada la migración a .NET Core?

Comencemos con algunas de las razones por las que podría querer pasar a .NET Core (o .NET 5). Hay algunos, por lo que no tenga en cuenta esta lista exhaustiva.

### <a name="cross-platform-support"></a>Compatibilidad multiplataforma

Las aplicaciones basadas en .NET Core son realmente multiplataforma y se pueden ejecutar en Windows, Linux y macOS. No solo los desarrolladores pueden usar el hardware que deseen, pero también puede hospedar la aplicación en cualquier lugar. Entre los ejemplos se incluyen de IIS local a Azure en la nube o de contenedores de Docker de Linux a dispositivos IoT.

### <a name="performance-and-scalability"></a>Rendimiento y escalabilidad

Las aplicaciones compiladas con .NET Core se ejecutan en [una de las pilas de tecnología más rápidas disponibles en cualquier lugar](https://www.techempower.com/benchmarks/#hw=ph&test=plaintext). Las aplicaciones MVC de ASP.NET a menudo ven mejoras de rendimiento en ASP.NET Core, especialmente si se han actualizado para aprovechar algunas de las nuevas características disponibles en .NET Core.

### <a name="cloud-native"></a>Nativo de la nube

Por los motivos anteriores y otros, las aplicaciones .NET Core son adecuadas para ejecutarse en entornos de hospedaje en la nube. Las aplicaciones .NET Core ligeras y rápidas pueden implementarse en App de Azure servicios o contenedores y escalarse horizontalmente según sea necesario para satisfacer la demanda inmediata del sistema.

### <a name="maintainable"></a>Fácil

En el caso de muchas aplicaciones, mientras continúan cumpliendo las necesidades empresariales y de los clientes, la deuda técnica ha acumulado y el mantenimiento de la aplicación ha crecido. ASP.NET Core aplicaciones se comprueban más fácilmente que las aplicaciones de ASP.NET MVC, lo que facilita su refactorización y su extensión con confianza.

### <a name="modular"></a>Modular

ASP.NET Core es modular, con paquetes NuGet como parte de primera clase del marco. Las aplicaciones compiladas para .NET Core admiten la inserción de dependencias, lo que facilita la creación de soluciones desde cualquier implementación que sea necesaria para un entorno determinado. La creación de microservicios con .NET Core es más fácil que con ASP.NET MVC con su dependencia en IIS, que abre opciones adicionales para dividir aplicaciones de gran tamaño en módulos más pequeños.

### <a name="modern"></a>Moderna

Mantenerse en una moderna pila de tecnología desarrollada activamente tiene un gran sistema de ventajas. Las nuevas características y las características del lenguaje C# solo se agregarán a .NET Core. El .NET Framework ha tenido su última versión con la versión 4,8 y las versiones de C# más allá de 8 no tendrán como destino .NET Framework. Aunque ASP.NET MVC seguirá siendo compatible con Microsoft durante muchos años, es probable que los desarrolladores de software de .NET mejores y más brillantes quieran usar el marco de trabajo de .NET Core más moderno, con todas las ventajas que ofrece (solo algunos de los cuales se resumen anteriormente). La búsqueda de los desarrolladores con los conocimientos necesarios para mantener una aplicación ASP.NET MVC comenzará a convertirse en un desafío en algún momento, al igual que buscará ayuda en línea y asistencia para la solución de problemas. Probablemente no haya muchas nuevas entradas de blog que se escriben sobre ASP.NET MVC 5, mientras que hay mucha escritura para .NET 5,0, por ejemplo.

Hay muchas razones atractivas que se deben tener en cuenta para migrar a .NET Core, lo que supuestamente es el motivo por el que está leyendo este libro. Pero vamos a tener en cuenta algunas desventajas y motivos por los que puede que tenga más sentido permanecer en el .NET Framework.

## <a name="when-is-net-framework-appropriate"></a>¿Cuándo es .NET Framework adecuado?

La mayor razón para permanecer en .NET Framework es cuando una aplicación no está bajo el desarrollo activo y no se beneficiaría sustancialmente de las ventajas mencionadas anteriormente. En ese caso, probablemente no haya un buen caso empresarial para incurrir en el costo de migrar la aplicación. Si su aplicación puede beneficiarse de las ventajas que ofrece .NET Core, es posible que tenga que seguir .NET Framework Si necesita algunas tecnologías que no están disponibles en .NET Core. Hay algunas [tecnologías de .net que no están disponibles en .net Core](../../core/porting/net-framework-tech-unavailable.md), como AppDomains, Remoting, seguridad de acceso del código (CAS), transparencia de seguridad y `System.EnterpriseServices` . Aquí se incluye un breve resumen de estas tecnologías y sus alternativas. Para obtener instrucciones más detalladas, consulte la documentación de.

### <a name="application-domains"></a>Dominios de aplicación

Los dominios de aplicación aíslan las aplicaciones entre sí. Los AppDomains requieren compatibilidad en tiempo de ejecución y pueden ser costosos. No se admite la creación de dominios de aplicación adicionales y no hay planes para agregar esta funcionalidad a .NET Core en el futuro. En el caso del aislamiento del código, use contenedores o procesos independientes como alternativa. Algunos clientes usan AppDomains como forma de descargar ensamblados. En .NET Core [AssemblyLoadContext](https://docs.microsoft.com/dotnet/standard/assembly/unloadability) proporciona una manera alternativa de descargar los ensamblados.

### <a name="wcf"></a>WCF

WCF de servidor no se admite en .NET Core. .NET Core es compatible con clientes de WCF, pero no con hosts de WCF. Las aplicaciones que requieren esta funcionalidad deberán actualizarse a una tecnología de comunicación diferente (como gRPC o REST) como parte de una migración.

Hay un [Puerto de cliente de WCF disponible en .net Foundation](../../core/dotnet-five.md#windows-communication-foundation). Es totalmente de código abierto, multiplataforma y es compatible con Microsoft. También hay un [proyecto de CoreWCF](https://github.com/CoreWCF/CoreWCF) compatible con la comunidad que *no* es compatible oficialmente con Microsoft.

Para obtener más información sobre cómo migrar de WCF a gRPC, consulte el libro electrónico [de gRPC para desarrolladores de WCF](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/) .

### <a name="remoting"></a>Comunicación remota

La comunicación remota de .NET se identificó como una arquitectura problemática. Se usa para la comunicación entre dominios de aplicaciones, una funcionalidad que ya no es compatible. Además, la comunicación remota requiere la compatibilidad con el runtime, cuyo mantenimiento resulta caro. Por estos motivos, .NET Remoting no es compatible con .NET Core y el equipo del producto no tiene previsto agregar soporte técnico en el futuro. Hay varias implementaciones y estrategias de mensajería alternativas que puede usar para reemplazar la comunicación remota en las aplicaciones de .NET Core.

### <a name="code-access-security-cas-and-security-transparency"></a>Seguridad de acceso del código (CAS) y transparencia de seguridad

Ninguna de estas tecnologías es compatible con .NET Core. En su lugar, se recomienda usar los límites de seguridad proporcionados por el sistema operativo. Por ejemplo, virtualización, contenedores o cuentas de usuario. Ejecutar procesos con el conjunto mínimo de privilegios necesarios.

## <a name="references"></a>Referencias

[Tecnologías de .NET Framework no disponibles en .NET Core](../../core/porting/net-framework-tech-unavailable.md)

>[!div class="step-by-step"]
>[Anterior](introduction.md)
>[Siguiente](migrate-aspnet-core-2-1.md)
