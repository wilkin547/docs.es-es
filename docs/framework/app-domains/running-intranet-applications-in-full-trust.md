---
title: "Ejecutar aplicaciones de Intranet con plena confianza | Microsoft Docs"
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
  - "plena confianza, ejecutar aplicaciones de intranet en"
  - "aplicaciones de intranet, ejecutar con plena confianza"
  - "ejecutar aplicaciones de intranet con plena confianza"
ms.assetid: ee13c0a8-ab02-49f7-b8fb-9eab16c6c4f0
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# Ejecutar aplicaciones de Intranet con plena confianza
A partir de .NET Framework versión 3.5 Service Pack 1 \(SP1\), las aplicaciones y sus ensamblados de biblioteca se puede ejecutar como ensamblados de plena confianza desde un recurso compartido de red.  Las pruebas de zona <xref:System.Security.SecurityZone> se agregan automáticamente a los ensamblados que se cargan desde un recurso compartido de la intranet.  Esta evidencia proporciona a dichos ensamblados el mismo conjunto de permisos concedidos \(que normalmente son de plena confianza\) que el de los ensamblados que se encuentran en el equipo.  Esta funcionalidad no se utiliza en las aplicaciones ClickOnce ni en las aplicaciones diseñadas para ejecutarse en un host.  
  
## Reglas de los ensamblados de bibliotecas  
 Las reglas siguientes se aplican a los ensamblados que se cargan mediante un archivo ejecutable de un recurso compartido de red:  
  
-   Los ensamblados de bibliotecas deben encontrarse en la misma carpeta que el ensamblado ejecutable.  A los ensamblados que se encuentran en una subcarpeta o a los que se hace referencia en una ruta de acceso diferente no se les asigna el conjunto de permisos concedidos de plena confianza.  
  
-   Si el ejecutable carga con retraso un ensamblado, debe utilizar la misma ruta de acceso que se utilizó para iniciar el ejecutable.  Por ejemplo, si el \\*share* de*network\-computer*de \\\\ de acción se asigna a una letra de unidad y el ejecutable se ejecuta desde esa ruta, a los ensamblados cargados por la aplicación ejecutable mediante la ruta de acceso de red plena confianza.  Para cargar con retraso un ensamblado en la zona <xref:System.Security.SecurityZone>, el ejecutable debe utilizar la ruta de acceso de la letra de unidad.  
  
## Restaurar la directiva de intranet anterior  
 En versiones anteriores de .NET Framework, a los ensamblados compartidos se les concedía la evidencia de zona <xref:System.Security.SecurityZone>.  Había que especificar la directiva de seguridad de acceso del código para conceder plena confianza a un ensamblado en un recurso compartido.  
  
 Este nuevo comportamiento es el valor predeterminado de los ensamblados de intranet.  Puede recuperar el comportamiento anterior y proporcionar la evidencia <xref:System.Security.SecurityZone>; para ello, hay que configurar una clave del Registro que afecta a todas las aplicaciones del equipo.  Este proceso es diferente para los equipos de 32 bits y de 64 bits:  
  
-   En equipos de 32 bits, cree una subclave bajo la clave HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework en el Registro del sistema.  Utilice el nombre de clave LegacyMyComputerZone con un valor DWORD de 1.  
  
-   En equipos de 64 bits, cree una subclave bajo la clave HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework en el Registro del sistema.  Utilice el nombre de clave LegacyMyComputerZone con un valor DWORD de 1.  Cree la misma subclave bajo la clave HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework.  
  
## Vea también  
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)