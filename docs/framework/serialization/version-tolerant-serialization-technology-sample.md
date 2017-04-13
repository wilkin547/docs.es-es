---
title: "Ejemplo de Version Tolerant Serialization Technology | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2a183664-bfbf-4ff0-96f6-c836284ea916
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Ejemplo de Version Tolerant Serialization Technology
[Descargar ejemplo](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/VTS.zip.exe)  
  
 Este ejemplo muestra las características de tolerancia a versiones de .NET Serialization.En el ejemplo se generan aplicaciones que utilizan versiones diferentes de una clase <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> para serializar y deserializar datos.A pesar de la presencia de versiones de tipo diferentes, las aplicaciones se comunican de forma transparente.Para obtener más información, vea [Serialización tolerante a versiones](../../../docs/framework/serialization/version-tolerant-serialization.md).  
  
### Para generar el ejemplo desde el símbolo del sistema  
  
1.  Abra una ventana del símbolo del sistema y navegue hasta uno de los subdirectorios específicos del lenguaje \(en V1 Application o V2 Application\) del ejemplo.  
  
2.  Escriba **msbuild.exe\<ver\> application.sln** en la línea de comandos \(donde \<ver\> es v1 o v2\).  
  
### Para compilar el ejemplo mediante Visual Studio  
  
1.  Abra el [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] y navegue hasta uno de los subdirectorios específicos del lenguaje del ejemplo.  
  
2.  Navegue hasta el subdirectorio V1 Application del directorio que seleccionó en el paso anterior.  
  
3.  Haga doble clic en el icono V1 Application.sln para abrir el archivo en Visual Studio.  
  
4.  En el menú **Compilar**, haga clic en **Compilar solución**.  
  
5.  Navegue hasta el subdirectorio V2 Application y repita los dos pasos anteriores para generar la aplicación V2 Application.  
  
 Las aplicaciones se generarán en los subdirectorios predeterminados \\bin o \\bin\\Debug de sus directorios de proyecto respectivos.  
  
### Para ejecutar el ejemplo  
  
1.  En la ventana del símbolo del sistema, navegue hasta el subdirectorio específico del lenguaje que seleccionó cuando generó las aplicaciones de ejemplo.  
  
2.  Escriba **runme.cmd** en la línea de comandos para ejecutar ambas aplicaciones a la vez.  
  
 Otra opción es navegar a los directorios que contienen las nuevas aplicaciones ejecutables y ejecutarlas secuencialmente.  
  
> [!NOTE]
>  En el ejemplo se generan aplicaciones de consola.Para ver el resultado, debe iniciarlas y ejecutarlas en una ventana del símbolo del sistema.  
  
## Vea también  
 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>   
 <xref:System.IO.FileStream>