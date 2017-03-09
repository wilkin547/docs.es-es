---
title: "Se cre&#243; una referencia al ensamblado de interoperabilidad &#39;&lt;ensamblado1&gt;&#39; incrustado debido a una referencia indirecta a dicho ensamblado desde el ensamblado &#39;&lt;ensamblado2&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc40059"
  - "bc40059"
helpviewer_keywords: 
  - "BC40059"
  - "VBC40059"
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Se cre&#243; una referencia al ensamblado de interoperabilidad &#39;&lt;ensamblado1&gt;&#39; incrustado debido a una referencia indirecta a dicho ensamblado desde el ensamblado &#39;&lt;ensamblado2&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Se creó una referencia al ensamblado de interoperabilidad '\<ensamblado1\>' incrustado debido a una referencia indirecta a dicho ensamblado desde el ensamblado '\<ensamblado2\>'.Considere cambiar la propiedad 'Incrustar tipos de interoperabilidad' en alguno de los ensamblados.  
  
 Ha agregado una referencia a un ensamblado \(ensamblado1\) cuya propiedad `Embed Interop Types` está establecida en `True`.  Esto indica al compilador que incruste la información de tipo de interoperabilidad desde este ensamblado.  Sin embargo, el compilador no puede incrustar información de tipo de interoperabilidad desde este ese ensamblado porque otro ensamblado al que ha hecho referencia \(ensamblado2\) también hace referencia a este ensamblado \(ensamblado1\) y tiene la propiedad `Embed Interop Types` establecida en `False`.  
  
> [!NOTE]
>  Para el compilador de línea de comandos, el establecimiento de la propiedad `Embed Interop Types` de una referencia a ensamblado en `True` equivale a hacer referencia al ensamblado utilizando la opción `/link`.  
  
 **Identificador de error:** BC40059  
  
### Para resolver esta advertencia  
  
-   Para incrustar información de tipo de interoperabilidad para ambos ensamblados, establezca la propiedad `Embed Interop Types` de todas las referencias a ensamblado1 en `True`.  
  
-   Para quitar la advertencia, puede establecer la propiedad `Embed Interop Types` de ensamblado1 en `False`.  En este caso, la información de tipo de interoperabilidad se proporciona mediante un ensamblado de interoperabilidad primario \(PIA\).  
  
## Vea también  
 [\/link](../../../visual-basic/reference/command-line-compiler/link.md)   
 [Programming with Primary Interop Assemblies](http://msdn.microsoft.com/es-es/306fa1d6-0703-4004-9e93-d0a57f1be81e)