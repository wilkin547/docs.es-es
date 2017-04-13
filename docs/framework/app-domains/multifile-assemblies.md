---
title: "Ensamblados de varios archivos | Microsoft Docs"
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
  - "ensamblados [.NET Framework], de múltiples archivos"
  - "manifiesto del ensamblado, ensamblados de múltiples archivos"
  - "módulos de código"
  - "compiladores de línea de comandos"
  - "compilar ensamblados"
  - "punto de entrada de un ensamblado"
  - "ensamblados de múltiples archivos"
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Ensamblados de varios archivos
Es posible crear ensamblados de múltiples archivos usando compiladores de la línea de comandos o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] con Visual C\+\+.  Uno de los archivos del ensamblado debe contener el manifiesto del ensamblado.  Un ensamblado que inicia una aplicación debe contener también un punto de entrada, como los métodos Main o WinMain.  
  
 Por ejemplo, suponga que tiene una aplicación que contiene dos módulos de código, Client.cs y Stringer.cs.  Stringer.cs crea el espacio de nombres `myStringer` al que hace referencia el código en Client.cs.  Client.cs contiene el método `Main`, que es el punto de entrada de la aplicación.  En este ejemplo, se compilan los dos módulos de código y, después, se crea un tercer archivo que contiene el manifiesto del ensamblado, que inicia la aplicación.  El manifiesto del ensamblado hace referencia a los dos módulos, `Client` y `Stringer`.  
  
> [!NOTE]
>  Los ensamblados de múltiples archivos sólo pueden tener un punto de entrada, aunque el ensamblado tenga varios módulos de código.  
  
 Existen varias razones para crear un ensamblado de varios archivos:  
  
-   Para combinar módulos escritos en lenguajes distintos.  Esta es la razón más frecuente para crear ensamblados de varios archivos.  
  
-   Para optimizar la descarga de una aplicación mediante la colocación de los tipos que se usan poco en un módulo que sólo se descarga cuando se necesitan.  
  
    > [!NOTE]
    >  Si se van a crear aplicaciones que se descargarán mediante la etiqueta `<object>` con Microsoft Internet Explorer, es importante que se creen ensamblados de múltiples archivos.  En este caso, se crea un archivo aparte de los módulos de código, que contiene sólo el manifiesto del ensamblado.  Internet Explorer descarga primero el manifiesto del ensamblado y, a continuación, crea subprocesos de trabajo para descargar los módulos o ensamblados adicionales necesarios.  Mientras se está descargando el archivo que contiene el manifiesto del ensamblado, Internet Explorer no responderá a los datos proporcionados por el usuario.  Cuanto más pequeño sea el archivo que contiene el manifiesto del ensamblado, menos tiempo estará Internet Explorer sin responder al usuario.  
  
-   Para combinar módulos de código escritos por varios programadores.  Si bien cada programador puede compilar cada módulo de código en un ensamblado, esto puede hacer que se expongan públicamente algunos tipos que no se exponen si todos los módulos se ubican en un ensamblado de varios archivos.  
  
 Una vez que se ha creado el ensamblado, se puede firmar el archivo que contiene el manifiesto del ensamblado \(y, por lo tanto el ensamblado\) o se puede dar al archivo \(y al ensamblado\) un nombre seguro y colocarlo en la caché global de ensamblados.  
  
## Vea también  
 [Cómo: Compilar un ensamblado de varios archivos](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)