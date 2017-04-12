---
title: Valor de tipo &quot;&lt;NombreTipo1&gt;&quot;no se puede convertir a&quot;&lt;en NombreTipo2&gt;&quot; (varias referencias de archivo) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
dev_langs:
- VB
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 732291ce9c4b83bb9fc7e83fbbc2a8da9748db59
ms.lasthandoff: 03/13/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a>Valor de tipo '&lt;NombreTipo1&gt;'no se puede convertir a'&lt;en NombreTipo2&gt;' (varias referencias de archivo)
Valor de tipo '\<NombreTipo1 >' no se puede convertir a '\<en NombreTipo2 >'. Discrepancia de tipo podría ser debido a la combinación de una referencia a '\<filepath1 >' proyecto '\<projectname1 >' con una referencia a '\<ruta_archivo2 >' proyecto '\<projectname2 >'. Si ambos ensamblados son idénticos, intente reemplazar estas referencias para que ambas procedan de la misma ubicación.  
  
 En una situación donde un proyecto realiza más de una referencia de archivo a un ensamblado, el compilador no puede garantizar que se puede convertir un tipo a otro.  
  
 Cada referencia de archivo especifica una ruta de acceso y el nombre del archivo de salida de un proyecto (normalmente un archivo DLL). El compilador no puede garantizar que los archivos de salida procedan del mismo origen, ni que representen la misma versión del mismo ensamblado. Por lo tanto, no puede garantizar que los tipos de las distintas referencias son del mismo tipo, o incluso que uno puede convertirse a otro.  
  
 Puede utilizar una referencia de archivo si sabe que los ensamblados de referencia tienen la misma identidad de ensamblado. La *identidad del ensamblado* incluye el nombre, la versión, la clave pública, si existe, y la referencia cultural del ensamblado. Esta información identifica de forma exclusiva el ensamblado.  
  
 **Id. de error:** BC30961  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si los ensamblados de referencia tienen la misma identidad de ensamblado, quite o reemplace una de las referencias de archivo de manera que hay sólo una referencia de archivo.  
  
-   Si los ensamblados de referencia no tienen la misma identidad de ensamblado, cambie su código para que no intente convertir el tipo de uno a un tipo en otro.  
  
## <a name="see-also"></a>Vea también  
 [Conversiones de tipos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Administrar referencias en un proyecto](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [Cómo: Agregar o quitar referencias con el cuadro de diálogo Agregar referencia](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
