---
title: "Un valor de tipo &#39;&lt;nombre de tipo 1&gt;&#39; no se puede convertir a &#39;&lt;nombre de tipo 2&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30955"
  - "bc30955"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30955"
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Un valor de tipo &#39;&lt;nombre de tipo 1&gt;&#39; no se puede convertir a &#39;&lt;nombre de tipo 2&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un valor de tipo '\<nombre de tipo 1\>' no se puede convertir en '\<nombre de tipo 2\>'.La falta de coincidencia de los tipos se podría deber a la mezcla de una referencia de archivo con una referencia de proyecto al ensamblado '\<nombre de ensamblado\>'.Pruebe a reemplazar la referencia de archivo a '\<ruta de archivo\>' en el proyecto '\<nombre de proyecto 1\>' con una referencia de proyecto a '\<nombre de proyecto 2\>.'  
  
 En una situación en la que un proyecto realiza tanto una referencia de proyecto como una referencia de archivo, el compilador no puede garantizar que un tipo se pueda convertir en otro.  
  
 El pseudocódigo siguiente muestra una situación que puede generar este error.  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 El proyecto `P1` realiza una referencia de proyecto indirecta a través del proyecto `P2` al proyecto `P3` y una referencia de archivo directa a `P3`.  La declaración de `commonObject` utiliza la referencia de archivo a `P3`, mientras la llamada a `P2.getCommonClass` utiliza la referencia de proyecto a `P3`.  
  
 El problema en esta situación es que la referencia de archivo especifica una ruta y un nombre de archivo para el archivo de salida de `P3` \(generalmente p3.dll\), en tanto que las referencias de proyecto identifican el proyecto de origen \(`P3`\) por nombre de proyecto.  Así, el compilador no puede garantizar que el tipo `P3.commonClass` procede del mismo código fuente desde las dos referencias diferentes.  
  
 Esta situación se produce normalmente cuando se mezclan las referencias de proyecto y referencias de archivo.  En la ilustración anterior, el problema no se produciría si `P1` realizase una referencia de proyecto directa a `P3` en lugar de una referencia de archivo.  
  
 **Identificador de error:** BC30955  
  
### Para corregir este error  
  
-   Cambie la referencia de archivo a una referencia de proyecto.  
  
## Vea también  
 [Conversiones de tipos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Administrar referencias en un proyecto](/visual-studio/ide/managing-references-in-a-project)   
 [Cómo: Agregar o quitar referencias utilizando el cuadro de diálogo Agregar referencia](http://msdn.microsoft.com/es-es/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)