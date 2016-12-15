---
title: "&lt;summary&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<summary>"
  - "summary"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<summary> (etiqueta XML) [C#]"
  - "summary (etiqueta XML) [C#]"
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
caps.latest.revision: 17
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;summary&gt; (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

## Sintaxis  
  
```  
<summary>description</summary>  
```  
  
#### Parámetros  
 `description`  
 Resumen del objeto.  
  
## Comentarios  
 La etiqueta \<summary\> se utiliza para describir un tipo o un miembro de tipo.  Utilice [\<remarks\>](../../../csharp/programming-guide/xmldoc/remarks.md) para suministrar información adicional a una descripción de tipo.  Use el atributo [cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) para que herramientas de documentación como [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061) puedan crear hipervínculos internos a las páginas de documentación de los elementos de código.  
  
 El texto de la etiqueta \<summary\> es la única fuente de información sobre el tipo en IntelliSense y también se muestra en el [Object Browser Window](http://msdn.microsoft.com/es-es/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda).  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  Para crear la documentación final basándose en el archivo generado por el compilador, se puede crear una herramienta personalizada o usar una herramienta como [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061).  
  
## Ejemplo  
 [!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]  
  
 En el ejemplo anterior, se produce el siguiente archivo XML.  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:DotNetEvents.TestClass">  
            text for class TestClass  
        </member>  
        <member name="M:DotNetEvents.TestClass.DoWork(System.Int32)">  
            <summary>DoWork is a method in the TestClass class.  
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>  
            <seealso cref="M:DotNetEvents.TestClass.Main"/>  
            </summary>  
        </member>  
        <member name="M:DotNetEvents.TestClass.Main">  
            text for Main  
        </member>  
    </members>  
</doc>  
```  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo convertir una referencia `cref` en un tipo genérico.  
  
 [!code-cs[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]  
  
 En el ejemplo anterior, se produce el siguiente archivo XML.  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:ExtensionMethodsDemo1.A">  
            <summary cref="T:ExtensionMethodsDemo1.C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.B">  
            <summary cref="T:C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.C`1">  
            <summary cref="T:ExtensionMethodsDemo1.A">  
            </summary>  
            <typeparam name="T"></typeparam>  
        </member>  
    </members>  
</doc>  
  
```  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)