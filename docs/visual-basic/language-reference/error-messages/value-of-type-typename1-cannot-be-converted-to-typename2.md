---
title: Valor de tipo &#39; &lt;typename1&gt; &#39; no se puede convertir a &#39; &lt;nombredetipo2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: 9b3c029ed7bf73ff92dba65438d797b27fa135f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a>Valor de tipo &#39; &lt;typename1&gt; &#39; no se puede convertir a &#39; &lt;nombredetipo2&gt;&#39;
Valor de tipo '\<NombreTipo1 >' no se puede convertir a '\<nombredetipo2 >'. Error de coincidencia de tipo podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado '\<assemblyname >'. Intente reemplazar la referencia de archivo a '\<filepath >' en el proyecto '\<projectname1 >' con una referencia de proyecto a '\<projectname2 >'.  
  
 En una situación donde un proyecto hace una referencia de proyecto y una referencia de archivo, el compilador no puede garantizar que se puede convertir un tipo a otro.  
  
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
  
 Proyecto `P1` hace una referencia de proyecto indirecta a través del proyecto `P2` al proyecto `P3`y también una referencia de archivo directa a `P3`. La declaración de `commonObject` utiliza la referencia de archivo a `P3`, mientras que la llamada a `P2.getCommonClass` usa la referencia al proyecto `P3`.  
  
 El problema en esta situación es que la referencia de archivo especifica una ruta de acceso y nombre del archivo de salida de `P3` (generalmente p3.dll tanto), mientras que las referencias de proyecto identifican el proyecto de origen (`P3`) por nombre de proyecto. Por este motivo, el compilador no puede garantizar que el tipo `P3.commonClass` proceden del mismo código fuente a través de las dos referencias diferentes.  
  
 Esta situación se produce normalmente cuando las referencias de proyecto y se mezclan las referencias de archivo. En la ilustración anterior, el problema no se producirían si `P1` realiza una referencia de proyecto directa `P3` en lugar de una referencia de archivo.  
  
 **Id. de error:** BC30955  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Cambiar la referencia de archivo a una referencia de proyecto.  
  
## <a name="see-also"></a>Vea también  
 [Conversiones de tipos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)  
 
