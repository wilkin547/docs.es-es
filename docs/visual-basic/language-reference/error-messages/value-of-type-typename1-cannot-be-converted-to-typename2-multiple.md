---
title: Valor de tipo &#39; &lt;typename1&gt; &#39; no se puede convertir a &#39; &lt;nombredetipo2&gt; &#39; (varias referencias de archivo)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 41c18160be9b546f8b525376fa06bc0eca6c117a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a>Valor de tipo &#39; &lt;typename1&gt; &#39; no se puede convertir a &#39; &lt;nombredetipo2&gt; &#39; (varias referencias de archivo)
Valor de tipo '\<NombreTipo1 >' no se puede convertir a '\<nombredetipo2 >'. Discordancia de tipos puede deberse a la combinación de una referencia de archivo a '\<rutaaccesoarchivo1 >' en el proyecto '\<projectname1 >' con una referencia de archivo a '\<rutaaccesoarchivo2 >' en el proyecto '\<projectname2 >'. Si ambos ensamblados son idénticos, intente reemplazar estas referencias para que ambas procedan de la misma ubicación.  
  
 En una situación donde un proyecto hace más de una referencia de archivo a un ensamblado, el compilador no puede garantizar que se puede convertir un tipo a otro.  
  
 Cada referencia de archivo especifica una ruta de acceso y nombre del archivo de salida de un proyecto (normalmente un archivo DLL). El compilador no puede garantizar que los archivos de salida procedan del mismo origen, ni que representen la misma versión del mismo ensamblado. Por lo tanto, no puede garantizar que los tipos de las distintas referencias son del mismo tipo, o incluso que uno puede convertirse a otro.  
  
 Puede usar una referencia de archivo si sabe que los ensamblados de referencia tienen la misma identidad de ensamblado. La *identidad del ensamblado* incluye el nombre, la versión, la clave pública, si existe, y la referencia cultural del ensamblado. Esta información identifica de forma exclusiva el ensamblado.  
  
 **Id. de error:** BC30961  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si los ensamblados de referencia tienen la misma identidad de ensamblado, quite o reemplace una de las referencias de archivo para que hay solo una única referencia de archivo.  
  
-   Si los ensamblados de referencia no tienen la misma identidad de ensamblado, a continuación, cambie el código para que no intente convertir el tipo de uno a un tipo en otro.  
  
## <a name="see-also"></a>Vea también  
 [Conversiones de tipos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)  
 
