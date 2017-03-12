---
title: "Un valor de tipo &#39;&lt;nombreDeTipo1&gt;&#39; no se puede convertir a &#39;&lt;nombreDeTipo2&gt;&#39; (varias referencias de archivo) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30961"
  - "bc30961"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30961"
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Un valor de tipo &#39;&lt;nombreDeTipo1&gt;&#39; no se puede convertir a &#39;&lt;nombreDeTipo2&gt;&#39; (varias referencias de archivo)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un valor de tipo '\<nombre de tipo 1\>' no se puede convertir en '\<nombre de tipo 2\>'.La falta de coincidencia de los tipos se podría deber a la mezcla de una referencia de archivo a '\<rutaDeAcceso1\>' en el proyecto '\<nombreDeProyecto1\>' con una referencia de archivo a '\<rutaDeAcceso2\>' en el proyecto '\<nombreDeProyecto2\>'Si ambos ensamblados son idénticos, pruebe a reemplazar estas referencias para que ambas sean de la misma ubicación.  
  
 En las situaciones en las que un proyecto haga mas de una referencia de archivo a un ensamblado, el compilador no podrá garantizar que un tipo se pueda convertir en otro.  
  
 Cada referencia de archivo especifica una ruta de acceso y un nombre de archivo para el archivo de salida de un proyecto \(normalmente un archivo DLL\).  El compilador no puede garantizar que los archivos de salida procedan del mismo origen, ni que representen la misma versión del mismo ensamblado.  Por tanto, no puede garantizar que los tipos de las distintas referencias sean iguales, ni siquiera que un tipo se pueda convertir al otro.  
  
 Si sabe que los ensamblados de referencia tienen la misma identidad de ensamblado, puede utilizar una única referencia de archivo.  La *identidad de ensamblado* incluye el nombre, la versión, la clave pública si existe y la referencia cultural del ensamblado.  Esta información identifica de forma única el ensamblado.  
  
 **Identificador de error:** BC30961  
  
### Para corregir este error  
  
-   Si el ensamblado de referencia tiene la misma identidad de ensamblado, quite o reemplace una de las referencias de archivo para que solamente haya una referencia de archivo.  
  
-   Si los ensamblados de referencia no tienen la misma identidad de ensamblado, cambie su código para que no intente convertir el tipo de uno de los ensamblados en el tipo del otro.  
  
## Vea también  
 [Conversiones de tipos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Administrar referencias en un proyecto](/visual-studio/ide/managing-references-in-a-project)   
 [Cómo: Agregar o quitar referencias utilizando el cuadro de diálogo Agregar referencia](http://msdn.microsoft.com/es-es/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)