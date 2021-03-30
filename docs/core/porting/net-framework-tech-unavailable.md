---
title: Tecnologías de .NET Framework no disponibles en .NET Core y .NET 5+
titleSuffix: ''
description: Obtenga más información sobre las tecnologías de .NET Framework que no están disponibles en .NET Core y .NET 5.0 y versiones posteriores.
author: cartermp
ms.date: 03/08/2021
ms.openlocfilehash: d8eccce7e36552e0d5396779936681227cb1e28a
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104875127"
---
# <a name="net-framework-technologies-unavailable-on-net-core-and-net-5"></a>Tecnologías de .NET Framework no disponibles en .NET Core y .NET 5+

Varias tecnologías disponibles para las bibliotecas de .NET Framework no están disponibles para su uso con .NET 5+ (y .NET Core), por ejemplo, dominios de aplicaciones, comunicación remota y seguridad de acceso del código (CAS). Si las bibliotecas dependen de una o varias de las tecnologías que se enumeran en esta página, tenga en cuenta los enfoques alternativos que se mencionan.

Para obtener más información sobre la compatibilidad de API, vea [Cambios importantes en .NET](../compatibility/breaking-changes.md).

## <a name="application-domains"></a>Dominios de aplicación

Los dominios de aplicación aíslan las aplicaciones entre sí. Los dominios de aplicación necesitan la compatibilidad con el entorno de ejecución y consumen muchos recursos. No se admite la creación de dominios de aplicación adicionales y no existen planes para agregar esta funcionalidad en el futuro. En el caso del aislamiento del código, use contenedores o procesos independientes como alternativa. Para cargar ensamblados de forma dinámica, use la clase <xref:System.Runtime.Loader.AssemblyLoadContext>.

Para facilitar la migración de código de .NET Framework, .NET 5+ expone parte de la superficie de la API <xref:System.AppDomain>. Algunas de las API funcionan con normalidad (por ejemplo, <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType>), algunos miembros no hacen nada (por ejemplo, <xref:System.AppDomain.SetCachePath%2A>) y algunos de ellos generan <xref:System.PlatformNotSupportedException> (por ejemplo, <xref:System.AppDomain.CreateDomain%2A>). Compruebe los tipos que usa con el [`System.AppDomain` origen de referencia](https://github.com/dotnet/runtime/blob/main/src/libraries/System.Private.CoreLib/src/System/AppDomain.cs) en el [repositorio de GitHub dotnet/runtime](https://github.com/dotnet/runtime). Asegúrese de seleccionar la rama que coincida con su versión implementada.

## <a name="remoting"></a>Comunicación remota

La comunicación remota de .NET no se admite en .NET 5+ (y .NET Core). La comunicación remota de .NET se ha identificado como una arquitectura problemática. Se usa para la comunicación entre dominios de aplicación, que ya no se admiten. Además, la comunicación remota necesita compatibilidad con el runtime, cuyo mantenimiento resulta caro.

Para la comunicación entre procesos, considere la posibilidad de usar mecanismos de comunicación entre procesos (IPC) como alternativa a la comunicación remota, como las clases <xref:System.IO.Pipes> o <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>.

En los equipos, utilice una solución basada en red como una alternativa. Si es posible, use un protocolo de texto sin formato con poca sobrecarga, como HTTP. Como opción, aquí se puede usar el [servidor web Kestrel](/aspnet/core/fundamentals/servers/kestrel), el que utiliza ASP.NET Core. También considere el uso de <xref:System.Net.Sockets> para escenarios de conexión entre equipos basada en red. Para obtener más opciones, vea [.NET Open Source Developer Projects: Messaging](https://github.com/Microsoft/dotnet/blob/master/dotnet-developer-projects.md#messaging) (Proyectos de desarrolladores de código abierto de .NET: mensajería).

## <a name="code-access-security-cas"></a>Seguridad de acceso del código (CAS)

El espacio aislado, que se basa en el runtime o en el marco para restringir qué recursos usa o ejecuta una aplicación administrada, [no es compatible con .NET Framework](../../framework/misc/code-access-security.md) y, por tanto, tampoco se admite en .NET Core y.NET 5+. Hay demasiados casos en .NET Framework y en el runtime en los que se produce una elevación de privilegios para continuar tratando la seguridad de acceso al código (CAS) como un límite de seguridad. Además, la seguridad de acceso del código dificulta más la implementación y suele tener implicaciones en el rendimiento correcto para las aplicaciones que no pretenden usar esta funcionalidad.

Use los límites de seguridad que proporciona el sistema operativo, como la virtualización, los contenedores o las cuentas de usuario para ejecutar procesos con el menor conjunto de privilegios.

## <a name="security-transparency"></a>Transparencia de seguridad

Como ocurre con la seguridad de acceso al código, la transparencia de seguridad separa el código del espacio aislado del código crítico de seguridad de manera declarativa, pero [ya no se admite como un límite de seguridad](../../framework/misc/security-transparent-code.md). Silverlight usa mucho esta característica.

Use los límites de seguridad que proporciona el sistema operativo, como la virtualización, los contenedores o las cuentas de usuario para ejecutar procesos con el menor conjunto de privilegios.

## <a name="systementerpriseservices"></a>System.EnterpriseServices

<xref:System.EnterpriseServices?displayProperty=fullName> (COM+) no es compatible con .NET Core y .NET 5+.

## <a name="workflow-foundation-and-wcf"></a>Workflow Foundation y WCF

Windows Workflow Foundation (WF) y Windows Communication Foundation (WCF) no se admiten en .NET 5 y versiones posteriores (incluido .NET Core). Para ver alternativas, consulte las páginas [CoreWF](https://github.com/UiPath/corewf) y [CoreWCF](https://github.com/CoreWCF/CoreWCF).

## <a name="see-also"></a>Vea también

- [Introducción a la portabilidad de .NET Framework a .NET](index.md)
