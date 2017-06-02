---
title: "C&#243;mo: Buscar ensamblados mediante DEVPATH | Microsoft Docs"
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
  - "configuración de las aplicaciones de .NET Framework, ensamblados"
  - "app.config (archivos), ubicaciones de ensamblados"
  - "archivos de configuración de la aplicación, especificar la ubicación de un ensamblado"
  - "ensamblados [.NET Framework], ubicación"
  - "DEVPATH"
  - "ubicar ensamblados"
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# C&#243;mo: Buscar ensamblados mediante DEVPATH
Es posible que los programadores deseen garantizar que un ensamblado compartido que van a compilar funciona correctamente con varias aplicaciones.  En lugar de poner constantemente el ensamblado en la caché global de ensamblados mientras dura el ciclo de programación, el programador puede crear una variable de entorno DEVPATH que señale al directorio de resultados de creación del ensamblado.  
  
 Por ejemplo, supongamos que se está compilando un ensamblado compartido denominado MySharedAssembly y que el directorio de resultados es C:\\MySharedAssembly\\Debug.  Se puede poner C:\\MySharedAssembly\\Debug en la variable DEVPATH.  Debe especificar el elemento de [\<developmentMode\>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) en el archivo de configuración del equipo.  Este elemento indica al Common Language Runtime que utilice DEVPATH para localizar ensamblados.  
  
 El ensamblado compartido lo debe poder detectar el motor en tiempo de ejecución.  Para especificar un directorio privado con el fin de resolver referencias de ensamblado, utilice [Elemento \<codeBase\>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) o [Elemento \<probing\>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) en un archivo de configuración, como se describe en [Especificar la ubicación de un ensamblado](../../../docs/framework/configure-apps/specify-assembly-location.md).  Asimismo puede colocar el ensamblado en un subdirectorio del directorio de la aplicación.  Para obtener más información, vea [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
> [!NOTE]
>  Se trata de una característica avanzada, sólo con fines de desarrollo.  
  
 En el ejemplo siguiente se muestra cómo se consigue que el motor en tiempo de ejecución busque ensamblados en los directorios que especifica la variable de entorno DEVPATH.  
  
## Ejemplo  
  
```  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 El valor predeterminado es false.  
  
> [!NOTE]
>  Utilice esta configuración sólo durante el proceso de desarrollo.  El motor en tiempo de ejecución no comprueba la versión de los ensamblados con nombre seguro que se encuentran en la variable DEVPATH.  Simplemente utiliza el primer ensamblado que encuentra.  
  
## Vea también  
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/es-es/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)