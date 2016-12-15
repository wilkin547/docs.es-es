---
title: "No se puede escribir en el archivo de resultados &#39;&lt;nombredearchivo&gt;&#39;: &lt;error&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31019"
  - "bc31019"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31019"
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# No se puede escribir en el archivo de resultados &#39;&lt;nombredearchivo&gt;&#39;: &lt;error&gt;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Se ha producido un problema al crear el archivo.  
  
 No se puede abrir un archivo de salida para escritura.  Puede que otro proceso haya abierto el archivo \(o la carpeta que lo contiene\) o puede que este tenga establecido el atributo de solo lectura.  
  
 A continuación indicamos las situaciones más habituales en la que un archivo se abre de forma exclusiva:  
  
-   La aplicación ya se está ejecutando y usando sus archivos.  Para solucionar este problema, asegúrese de que la aplicación no se está ejecutando.  
  
-   Otra aplicación ha abierto el archivo.  Para solucionar este problema, asegúrese de que ninguna otra aplicación está accediendo a los archivos.  No siempre queda del todo claro qué aplicación está accediendo a los archivos; en tal caso, reiniciar el equipo constituye la forma más sencilla de finalizar la aplicación.  
  
 Esta excepción se generará aun cuando solo haya un archivo de salida del proyecto marcado como de solo lectura.  
  
 **Identificador del error:** BC31019  
  
### Para corregir este error  
  
1.  Vuelva a compilar el programa para ver si el error se repite.  
  
2.  Si el error continúa, guarde el trabajo y reinicie [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].  
  
3.  Si el error continúa, reinicie el equipo.  
  
4.  Si el error se repite, reinstale [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
5.  Si el error persiste después de la reinstalación, informe al respecto a los Servicios de soporte técnico de Microsoft.  
  
### Para consultar los atributos de archivo en el Explorador de archivos  
  
1.  Abra la carpeta que le interese.  
  
2.  Haga clic en el icono **Vistas** y elija **Detalles**.  
  
3.  Haga clic con el botón secundario en el encabezado de columna y elija **Atributos** en la lista desplegable.  
  
### Para cambiar los atributos de un archivo o carpeta  
  
1.  En el **Explorador de archivos**, haga clic con el botón secundario en el archivo o carpeta y seleccione **Propiedades**.  
  
2.  En la sección **Atributos** de la pestaña **General**, desactive la casilla **Solo lectura**.  
  
3.  Presione **Aceptar**.  
  
## Vea también  
 [Hable con nosotros](/visual-studio/ide/talk-to-us)