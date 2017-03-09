---
title: "&lt;include&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "include"
  - "<include>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<include> (etiqueta XML) [C#]"
  - "include (etiqueta XML) [C#]"
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# &lt;include&gt; (Gu&#237;a de programaci&#243;n de C#)
## Sintaxis  
  
```  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### Parámetros  
 `filename`  
 El nombre del archivo XML que contiene la documentación.  El nombre de archivo se puede completar con una ruta de acceso.  Agregue `filename` entre comillas simples \(' '\).  
  
 `tagpath`  
 Ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`.  Ponga la ruta de acceso entre comillas simples \(' '\).  
  
 `name`  
 Especificador de nombre en la etiqueta que precede a los comentarios; `name` poseerá un `id`.  
  
 `id`  
 Identificador para la etiqueta que precede a los comentarios.  Ponga el id. entre comillas dobles \(" "\).  
  
## Comentarios  
 La etiqueta \<include\> permite hacer referencia a comentarios colocados en otro archivo que describen los tipos y miembros del código fuente.  Ésta es una alternativa al método habitual de colocar los comentarios de la documentación directamente en el archivo de código fuente.  Colocando la documentación en un archivo independiente, puede aplicar el control de código fuente a la documentación independientemente del código fuente.  Una persona puede tener el archivo de código fuente desprotegido y alguien más puede tener el archivo de documentación desprotegido.  
  
 La etiqueta \<include\> utiliza la sintaxis XPath de XML.  Consulte la documentación de XPath para conocer diversos modos de personalizar el uso de \<include\>.  
  
## Ejemplo  
 Este ejemplo utiliza varios archivos.  El primer archivo, que utiliza \<include\>, se muestra a continuación:  
  
 [!code-cs[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/include_1.cs)]  
  
 El segundo archivo, xml\_include\_tag.doc, contiene los siguientes comentarios de documentación:  
  
```  
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
  
## Resultado del programa  
 Se genera el siguiente resultado al compilar las clases Test y Test2 con la siguiente línea de comandos: `/doc:DocFileName.xml.` En Visual Studio, se especifica que la opción Comentarios de documento XML del panel Compilación del Diseñador de proyectos.  Cuando el compilador de C\# ve la etiqueta \<inclue\>, buscará comentarios de documentación en xml\_include\_tag.doc en lugar del archivo de código fuente actual.  A continuación, el compilador genera DocFileName.xml, este el archivo que es utilizado por herramientas de documentación como [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061) para crear la documentación final.  
  
```  
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
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)