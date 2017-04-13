---
title: "Resolver cargas de ensamblado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ensamblados [.NET Framework], resolver cargas"
  - "Dominios de aplicación, cargar ensamblados"
  - "resolver cargas de ensamblado"
  - "ensamblados [.NET Framework], cargar"
  - "dominios de aplicación, resolver cargas de ensamblado"
ms.assetid: 5099e549-f4fd-49fb-a290-549edd456c6a
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Resolver cargas de ensamblado
.NET Framework proporciona el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> para las aplicaciones que necesitan un mayor control sobre la carga de ensamblados.  Controlando este evento, la aplicación puede cargar un ensamblado en el contexto de carga desde fuera de las rutas de acceso de sondeo normales, seleccionar cuál de las diversas versiones del ensamblado se va a cargar, emitir un ensamblado dinámico y devolverlo, etc.  En este tema se proporcionan directrices para controlar el evento <xref:System.AppDomain.AssemblyResolve>.  
  
> [!NOTE]
>  Para resolver las cargas de ensamblados en el contexto de solo reflexión, use el evento <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=fullName> en su lugar.  
  
## Cómo funciona el evento AssemblyResolve  
 Cuando se registra un controlador para el evento <xref:System.AppDomain.AssemblyResolve>, se invoca el controlador siempre que el runtime no puede enlazarse a un ensamblado por nombre.  Por ejemplo, la llamada a los métodos siguientes desde código de usuario puede hacer que se genere el evento <xref:System.AppDomain.AssemblyResolve>:  
  
-   Sobrecarga del método <xref:System.AppDomain.Load%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> cuyo primer argumento es una cadena que representa el nombre para mostrar del ensamblado que se va a cargar \(es decir, la cadena devuelta por la propiedad <xref:System.Reflection.Assembly.FullName%2A?displayProperty=fullName>\).  
  
-   Sobrecarga del método <xref:System.AppDomain.Load%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> cuyo primer argumento es un objeto <xref:System.Reflection.AssemblyName> que identifica el ensamblado que se va a cargar.  
  
-   Sobrecarga del método <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>.  
  
-   Sobrecarga del método <xref:System.AppDomain.CreateInstance%2A?displayProperty=fullName> o <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=fullName> que crea instancias de un objeto a otro dominio de aplicación.  
  
### Qué hace el controlador de eventos  
 El controlador para el evento <xref:System.AppDomain.AssemblyResolve> recibe el nombre para mostrar del ensamblado que se va a cargar, en la propiedad <xref:System.ResolveEventArgs.Name%2A?displayProperty=fullName>.  Si el controlador no reconoce el nombre de ensamblado, devuelve NULL \(`Nothing` en Visual Basic, `nullptr` en Visual C\+\+\).  
  
 Si el controlador reconoce el nombre de ensamblado, puede cargar y devolver un ensamblado que satisfaga la solicitud.  En la lista siguiente se describen algunos escenarios de ejemplo.  
  
-   Si el controlador conoce la ubicación de una versión del ensamblado, puede cargar el ensamblado usando el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName>, y puede devolver el ensamblado cargado si se ejecuta correctamente.  
  
-   Si el controlador tiene acceso a una base de datos de ensamblados almacenados como matrices de bytes, puede cargar una matriz de bytes mediante una de las sobrecargas del método <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> que toma una matriz de bytes.  
  
-   El controlador puede generar un ensamblado dinámico y devolverlo.  
  
> [!NOTE]
>  El controlador debe cargar el ensamblado en el contexto de origen de carga, en el contexto de carga o sin contexto.  Si el controlador carga el ensamblado en el contexto de solo reflexión mediante el método <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=fullName>, el intento de carga que generó el evento <xref:System.AppDomain.AssemblyResolve> producirá un error.  
  
 Es responsabilidad del controlador de eventos devolver un ensamblado apropiado.  El controlador puede analizar el nombre para mostrar del ensamblado solicitado pasando el valor de propiedad <xref:System.ResolveEventArgs.Name%2A?displayProperty=fullName> al constructor <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29>.  A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], el controlador puede usar la propiedad <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName> para determinar si la solicitud actual es una dependencia de otro ensamblado.  Esta información puede ayudar a identificar un ensamblado que satisface la dependencia.  
  
 El controlador de eventos puede devolver una versión diferente del ensamblado que la versión solicitada.  
  
 En la mayoría de los casos, el ensamblado devuelto por el controlador aparece en el contexto de carga, independientemente del contexto en el que el controlador lo carga.  Por ejemplo, si el controlador usa el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> para cargar un ensamblado en el contexto de origen de carga, el ensamblado aparece en el contexto de carga cuando el controlador lo devuelve.  Sin embargo, en el caso siguiente el ensamblado aparece sin contexto cuando el controlador lo devuelve:  
  
-   El controlador carga un ensamblado sin contexto.  
  
-   La propiedad <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName> no es NULL.  
  
-   El ensamblado solicitante \(es decir, el ensamblado devuelto por la propiedad <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName>\) se cargó sin contexto.  
  
 Para obtener información sobre los contextos, vea la sobrecarga del método <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=fullName>.  
  
 Se pueden cargar varias versiones del mismo ensamblado en el mismo dominio de aplicación.  Este procedimiento no se recomienda, porque puede conducir a problemas de asignación de tipos.  Vea [Procedimientos recomendados para cargar ensamblados](../../../docs/framework/deployment/best-practices-for-assembly-loading.md).  
  
### Lo que el controlador de eventos no debe hacer  
 La regla principal para controlar el evento <xref:System.AppDomain.AssemblyResolve> es que no debe intentar devolver un ensamblado que no se reconoce.  Cuando se escribe el controlador, debe saber qué ensamblados pueden generar el evento.  El controlador debe devolver NULL para otros ensamblados.  
  
> [!IMPORTANT]
>  A partir de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], el evento <xref:System.AppDomain.AssemblyResolve> se genera para los ensamblados satélites.  Este cambio afecta a un controlador de eventos escrito para una versión anterior de .NET Framework, si el controlador intenta resolver todas las solicitudes de carga de ensamblados.  Los controladores de eventos que omiten los ensamblados no reconocen que no se ven afectados por este cambio: devuelven NULL y se siguen los mecanismos normales de reserva.  
  
 Al cargar un ensamblado, el controlador de eventos no debe usar ninguna de las sobrecargas del método <xref:System.AppDomain.Load%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> que pueden hacer que el evento <xref:System.AppDomain.AssemblyResolve> se genere de forma recursiva, porque puede dar lugar a un desbordamiento de pila. \(Vea la lista proporcionada anteriormente en este tema.\) Esto ocurre incluso si proporciona el control de excepciones para la solicitud de carga, ya que no se produce ninguna excepción hasta que todos los controladores de eventos hayan vuelto.  Por tanto, el código siguiente produce un desbordamiento de la pila si `MyAssembly` no se encuentra:  
  
 [!code-cpp[AssemblyResolveRecursive#1](../../../samples/snippets/cpp/VS_Snippets_CLR/assemblyresolverecursive/cpp/example.cpp#1)]
 [!code-csharp[AssemblyResolveRecursive#1](../../../samples/snippets/csharp/VS_Snippets_CLR/assemblyresolverecursive/cs/example.cs#1)]
 [!code-vb[AssemblyResolveRecursive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/assemblyresolverecursive/vb/example.vb#1)]  
  
## Vea también  
 [Procedimientos recomendados para cargar ensamblados](../../../docs/framework/deployment/best-practices-for-assembly-loading.md)   
 [Utilizar dominios de aplicación](../../../docs/framework/app-domains/use.md)