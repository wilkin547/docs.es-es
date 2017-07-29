---
title: "Cómo: Utilizar las características de documentación XML (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: eeee77db523bc0ad97f425d4ba8076ae5740dfe8
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a>Cómo: Utilizar las características de documentación XML (Guía de programación de C#)
En el ejemplo siguiente se proporciona una introducción básica de un tipo que se ha documentado.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  
  
 **// Este archivo .xml se generó con el ejemplo de código anterior.**  
**\<?xml version="1.0"?>**  
**\<doc>**  
 **\<assembly>**  
 **\<name>xmlsample\</name>**  
 **\</assembly>**  
 **\<members>**  
 **\<member name="T:SomeClass">**  
 **\<summary>**  
 **La documentación de resumen de nivel de clase va aquí.\</summary>**  
 **\<remarks>**  
 **Los comentarios más largos se pueden asociar con un tipo o miembro**   
 **con la etiqueta remarks\</remarks>**  
 **\</member>**  
 **\<member name="F:SomeClass.m_Name">**  
 **\<summary>**  
 **Almacén de la propiedad name\</summary>**  
 **\</member>**  
 **\<member name="M:SomeClass.#ctor">**  
 **\<summary>Constructor de clase.\</summary>**   
 **\</member>**  
 **\<member name="M:SomeClass.SomeMethod(System.String)">**  
 **\<summary>**  
 **Descripción para SomeMethod.\</summary>**  
 **\<param name="s"> La descripción de parámetro para s va aquí\</param>**  
 **\<seealso cref="T:System.String">**  
 **Puede usar el atributo cref en cualquier etiqueta para hacer referencia a un tipo o un miembro**   
 **y el compilador comprobará que la referencia existe. \</seealso>**  
 **\</member>**  
 **\<member name="M:SomeClass.SomeOtherMethod">**  
 **\<summary>**  
 **Otro método. \</summary>**  
 **\<returns>**  
 **Los resultados devueltos se describen con la etiqueta returns.\</returns>**  
 **\<seealso cref="M:SomeClass.SomeMethod(System.String)">**  
 **Observe el uso del atributo cref para hacer referencia a un método específico \</seealso>**  
 **\</member>**  
 **\<member name="M:SomeClass.Main(System.String[])">**  
 **\<summary>**  
 **Punto de entrada de la aplicación.**  
 **\</summary>**  
 **\<param name="args"> Lista de argumentos de la línea de comandos\</param>**  
 **\</member>**  
 **\<member name="P:SomeClass.Name">**  
 **\<summary>**  
 **Propiedad Name \</summary>**  
 **\<value>**  
 **Se usa una etiqueta value para describir el valor de la propiedad\</value>**  
 **\</member>**  
 **\</members>**  
**\</doc>**   
## <a name="compiling-the-code"></a>Compilar el código  
 Para compilar el ejemplo, escriba la siguiente línea de comandos:  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 Esto creará el archivo XML XMLsample.xml, que se puede ver en el explorador o mediante el comando TYPE.  
  
## <a name="robust-programming"></a>Programación sólida  
 La documentación XML empieza con ///. Cuando se crea un proyecto, el asistente agrega automáticamente unas líneas de inicio ///. El procesamiento de estos comentarios tiene algunas restricciones:  
  
-   La documentación debe ser XML con formato correcto. Si el XML no tiene el formato correcto, se generará una advertencia y el archivo de documentación incluirá un comentario en el que se indica que se detectó un error.  
  
-   Los desarrolladores pueden crear su propio conjunto de etiquetas, pero hay un conjunto de etiquetas recomendado (vea la sección con información adicional). Algunas de las etiquetas recomendadas tienen significados especiales:  
  
    -   La etiqueta \<param> se usa para describir parámetros. Si se usa, el compilador comprobará que el parámetro existe y que todos los parámetros se describen en la documentación. Si se produce un error en la comprobación, el compilador emite una advertencia.  
  
    -   El atributo `cref` se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código. El compilador comprobará si existe ese elemento de código. Si se produce un error en la comprobación, el compilador emite una advertencia. El compilador respeta todas las instrucciones `using` cuando busca un tipo descrito en el atributo `cref`.  
  
    -   IntelliSense usa la etiqueta \<summary> en Visual Studio para mostrar información adicional sobre un tipo o miembro.  
  
        > [!NOTE]
        >  El archivo XML no proporciona información completa sobre los tipos y los miembros (por ejemplo, no contiene información de tipos). Para obtener información completa sobre un tipo o miembro, debe usarse el archivo de documentación con reflexión en el tipo o miembro reales.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [/doc (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [Comentarios de documentación XML](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

