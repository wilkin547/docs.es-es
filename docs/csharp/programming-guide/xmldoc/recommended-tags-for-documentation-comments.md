---
title: 'Etiquetas recomendadas para comentarios de documentación: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: d17ff0b78d8ae40916447e8e12da7948a21e5717
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523369"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a>Etiquetas recomendadas para comentarios de documentación (Guía de programación de C#)
El compilador de C# procesa los comentarios de documentación de su código y les aplica formato como XML en un archivo cuyo nombre especifica en la opción de línea de comandos **/doc**. Para crear la documentación final basada en el archivo generado por el compilador, puede crear una herramienta personalizada o usar una herramienta como [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).  
  
 Las etiquetas se procesan en construcciones de código como tipos y miembros de tipo.  
  
> [!NOTE]
> Los comentarios de documentación no pueden aplicarse en un espacio de nombres.  
  
 El compilador procesará cualquier etiqueta que sea un XML válido. Las siguientes etiquetas proporcionan funciones de uso general en la documentación de usuario.  
  
## <a name="tags"></a>Etiquetas  
  
||||  
|---|---|---|  
|[\<c>](./code-inline.md)|[\<para>](./para.md)|[\<see>](./see.md)*|  
|[\<code>](./code.md)|[\<param>](./param.md)*|[\<seealso>](./seealso.md)*|  
|[\<example>](./example.md)|[\<paramref>](./paramref.md)|[\<summary>](./summary.md)|  
|[\<exception>](./exception.md)*|[\<permission>](./permission.md)*|[\<typeparam>](./typeparam.md)*|  
|[\<include>](./include.md)*|[\<remarks>](./remarks.md)|[\<typeparamref>](./typeparamref.md)|  
|[\<list>](./list.md)|[\<returns>](./returns.md)|[\<value>](./value.md)|  
  
 (* denota que el compilador comprueba la sintaxis).  
  
 Si quiere que aparezcan corchetes angulares en el texto de un comentario de documentación, utilice la codificación HTML de `<` y `>`, que es `&lt;` y `&gt;` respectivamente. Esta codificación se muestra en el ejemplo siguiente:
  
```csharp  
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [-doc (Opciones del compilador de C#)](../../language-reference/compiler-options/doc-compiler-option.md)
- [Comentarios de documentación XML](./index.md)
