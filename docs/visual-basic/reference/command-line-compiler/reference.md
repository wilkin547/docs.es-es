---
title: /Reference (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 12344dba82131d6be2c32127de287a6e9e3efa39
ms.lasthandoff: 03/13/2017

---
# <a name="reference-visual-basic"></a>/reference (Visual Basic)
Hace que el compilador disponer de información de tipo en los ensamblados especificados al proyecto que se está compilando.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`fileList`|Obligatorio. Lista delimitada por comas de nombres de archivo de ensamblado. Si el nombre de archivo contiene un espacio, encierre el nombre entre comillas.|  
  
## <a name="remarks"></a>Comentarios  
 Los archivos importados deben contener metadatos de ensamblado. Solo los tipos públicos son visibles fuera del ensamblado. El [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) opción importa metadatos de un módulo.  
  
 Si hace referencia a un ensamblado (ensamblado A) que hace referencia a otro ensamblado (ensamblado B), deberá hacer referencia al ensamblado B si:  
  
-   Un tipo en el ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.  
  
-   Se invoca un campo, propiedad, evento o un método que tiene un tipo de parámetro o tipo de valor devuelto del ensamblado B.  
  
 Utilice [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblado.  
  
 Para que el compilador reconozca un tipo en un ensamblado (no un módulo), debe obligársele a resolver el tipo. Un ejemplo de cómo se puede hacer es definir una instancia del tipo. Hay otras formas resolver los nombres de tipo en un ensamblado para el compilador. Por ejemplo, si se hereda de un tipo en un ensamblado, el nombre del tipo, a continuación, se convierte en el compilador conoce.  
  
 El archivo de respuesta Vbc.rsp, que normalmente se utilizan referencias [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] ensamblados, se utiliza de forma predeterminada. Utilice `/noconfig` si no desea que el compilador utilice Vbc.rsp.  
  
 La forma abreviada de `/reference` es `/r`.  
  
## <a name="example"></a>Ejemplo  
 El siguiente origen de código compila archivos`nput.vb` y hacer referencia a ensamblados de M`etad1.dll` y M`etad2.dll` para producir O`ut.exe`.  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Público](../../../visual-basic/language-reference/modifiers/public.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
