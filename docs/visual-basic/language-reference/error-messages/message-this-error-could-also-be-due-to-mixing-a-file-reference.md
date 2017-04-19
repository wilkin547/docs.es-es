---
title: "&lt;mensaje&gt; este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado &quot;&lt;assemblyname&gt;&quot; | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
dev_langs:
- VB
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a1806fd078fc05d966c718841e5b78c1323a43c2
ms.lasthandoff: 03/13/2017

---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a>&lt;mensaje&gt; este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado '&lt;assemblyname&gt;'
\<mensaje > este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado '\<assemblyname >. En este caso, intente reemplazar la referencia de archivo a '\<assemblyfilename >' proyecto '\<projectname1 >' con una referencia al proyecto '\<projectname2 >'.  
  
 Código del proyecto tiene acceso a un miembro de otro proyecto, pero la configuración de la solución no permite la [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador para resolver la referencia.  
  
 Para obtener acceso a un tipo definido en otro ensamblado, el [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador debe tener una referencia a dicho ensamblado. Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.  
  
 **Identificador de error:** BC30971  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este. Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.  
  
2.  En las propiedades del proyecto, agregue una referencia al proyecto que contiene el ensamblado que define el tipo que está usando.  
  
## <a name="see-also"></a>Vea también  
 [Administrar referencias en un proyecto](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Cómo: Agregar o quitar referencias utilizando el cuadro de diálogo Agregar referencia](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [NIB Cómo: modificar las propiedades de proyecto y opciones de configuración](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Solucionar problemas de referencias rotas](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)
