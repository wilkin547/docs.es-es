---
title: Valor de tipo &quot;&lt;NombreTipo1&gt;&quot;no se puede convertir a&quot;&lt;en NombreTipo2&gt;&quot; | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30955
- bc30955
dev_langs:
- VB
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: 12
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
ms.openlocfilehash: c973d5e2aa03d423e1dea8053946172655f08490
ms.lasthandoff: 03/13/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a>Valor de tipo '&lt;NombreTipo1&gt;'no se puede convertir a'&lt;en NombreTipo2&gt;'
Valor de tipo '\<NombreTipo1 >' no se puede convertir a '\<en NombreTipo2 >'. Error de coincidencia de tipo puede deberse a la mezcla de una referencia de archivo con una referencia de proyecto al ensamblado '\<assemblyname >'. Pruebe a reemplazar la referencia de archivo a '\<filepath >' proyecto '\<projectname1 >' con una referencia al proyecto '\<projectname2 >'.  
  
 En una situación donde un proyecto contiene una referencia de proyecto y una referencia de archivo, el compilador no puede garantizar que se puede convertir un tipo a otro.  
  
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
  
 Proyecto `P1` hace una referencia de proyecto indirecta a través del proyecto `P2` proyecto `P3`y también una referencia de archivo directa a `P3`. La declaración de `commonObject` utiliza la referencia de archivo a `P3`, mientras que la llamada a `P2.getCommonClass` utiliza la referencia de proyecto a `P3`.  
  
 El problema en esta situación es que la referencia de archivo especifica una ruta de acceso y el nombre del archivo de salida de `P3` (generalmente p3.dll tanto), mientras que las referencias de proyecto identifican el proyecto de origen (`P3`) por el nombre del proyecto. Por este motivo, el compilador no puede garantizar que el tipo `P3.commonClass` proceden del mismo código fuente a través de las dos referencias diferentes.  
  
 Esta situación se produce normalmente cuando las referencias de proyecto y se mezclan las referencias de archivo. En la ilustración anterior, el problema no se produciría si `P1` crea una referencia de proyecto directa a `P3` en lugar de una referencia de archivo.  
  
 **Id. de error:** BC30955  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Cambie la referencia de archivo a una referencia de proyecto.  
  
## <a name="see-also"></a>Vea también  
 [Conversiones de tipos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Administrar referencias en un proyecto](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [Cómo: Agregar o quitar referencias con el cuadro de diálogo Agregar referencia](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
