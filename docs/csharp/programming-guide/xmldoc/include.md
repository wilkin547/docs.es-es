---
title: "&lt;include&gt; (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- include
- <include>
dev_langs:
- CSharp
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: df0438dd742db802bb0f935d840006236d5d9bf9
ms.openlocfilehash: 0cabcc25c4e35027c600e4af2bccfad7f9db1514
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="ltincludegt-c-programming-guide"></a>&lt;include&gt; (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```xml  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### <a name="parameters"></a>Parámetros  
 `filename`  
 El nombre del archivo XML que contiene la documentación. El nombre de archivo se puede calificar con una ruta de acceso. Incluya `filename` entre comillas simples (' ').  
  
 `tagpath`  
 La ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`. Incluya la ruta de acceso entre comillas simples (' ').  
  
 `name`  
 El especificador de nombre en la etiqueta que precede a los comentarios; `name` tendrá un `id`.  
  
 `id`  
 El identificador de la etiqueta que precede a los comentarios. Ponga el identificador entre comillas dobles (" ").  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta \<include> le permite hacer referencia a comentarios colocados en otro archivo que describen los tipos y miembros en el código fuente. Esto es una alternativa a colocar los comentarios de documentación directamente en el archivo de código fuente. Al colocar la documentación en un archivo independiente, puede aplicar el control de código fuente a la documentación de forma independiente desde el código fuente. Una persona puede tener el archivo de código fuente extraído del repositorio y otra persona puede tener el archivo de documentación extraído del repositorio.  
  
 La etiqueta \<include> usa la sintaxis de XPath de XML. Consulte la documentación de XPath para ver formas de personalizar el uso de \<include>.  
  
## <a name="example"></a>Ejemplo  
 Este es un ejemplo de múltiples archivos. El primer archivo, que usa \<include>, se menciona a continuación:  
  
 [!code-cs[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]  
  
 El segundo archivo, xml_include_tag.doc, contiene los siguientes comentarios de documentación:  
  
```xml  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## <a name="program-output"></a>Resultados del programa  
 Se genera el siguiente resultado al compilar las clases Test y Test2 con la siguiente línea de comandos: `/doc:DocFileName.xml.` En Visual Studio, especifique la opción de comentarios de documentación XML en el panel de compilación del Diseñador de proyectos. Cuando el compilador de C# detecta la etiqueta \<include>, busca los comentarios de documentación en xml_include_tag.doc en lugar del archivo de código fuente actual. Después, el compilador genera DocFileName.xml y este es el archivo que usan las herramientas de documentación como [Sandcastle](https://github.com/EWSoftware/SHFB) para generar la documentación final.  
  
```xml  
<?xml version="1.0"?>   
<doc>   
    <assembly>   
        <name>xml_include_tag</name>   
    </assembly>   
    <members>   
        <member name="T:Test">   
            <summary>   
The summary for this type.   
</summary>   
        </member>   
        <member name="T:Test2">   
            <summary>   
The summary for this other type.   
</summary>   
        </member>   
    </members>   
</doc>   
```  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

