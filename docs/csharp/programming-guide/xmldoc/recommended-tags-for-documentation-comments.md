---
title: 'Etiquetas recomendadas para comentarios de documentación: guía de programación de C#'
description: Aprenda sobre las etiquetas recomendadas para los comentarios de la documentación. Vea una lista de etiquetas recomendadas y examine los recursos adicionales disponibles.
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: 65bca6f979c5ffd91507b571a4f049377315192d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381520"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a>Etiquetas recomendadas para comentarios de documentación (guía de programación de C#)

El compilador de C# procesa los comentarios de documentación de su código y les aplica formato como XML en un archivo cuyo nombre especifica en la opción de línea de comandos **/doc**. Para crear la documentación final basada en el archivo generado por el compilador, puede crear una herramienta personalizada o usar una herramienta como [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).

Las etiquetas se procesan en construcciones de código como tipos y miembros de tipo.

> [!NOTE]
> Los comentarios de documentación no pueden aplicarse en un espacio de nombres.  
  
 El compilador procesará cualquier etiqueta que sea un XML válido. Las siguientes etiquetas proporcionan funciones de uso general en la documentación de usuario.  
  
## <a name="tags"></a>Etiquetas  
  
|||||  
|---|---|---|---|
|[\<c>](./code-inline.md)|[\<para>](./para.md)|[\<see>](./see.md)*|[\<value>](./value.md)  
|[\<code>](./code.md)|[\<param>](./param.md)*|[\<seealso>](./seealso.md)*|  
|[\<example>](./example.md)|[\<paramref>](./paramref.md)|[\<summary>](./summary.md)|  
|[\<exception>](./exception.md)*|[\<permission>](./permission.md)*|[\<typeparam>](./typeparam.md)*|  
|[\<include>](./include.md)*|[\<remarks>](./remarks.md)|[\<typeparamref>](./typeparamref.md)|  
|[\<list>](./list.md)|[\<inheritdoc>](./inheritdoc.md)|[\<returns>](./returns.md)|
  
(\* denota que el compilador comprueba la sintaxis).

Si quiere que aparezcan corchetes angulares en el texto de un comentario de documentación, utilice la codificación HTML de `<` y `>`, que es `&lt;` y `&gt;` respectivamente. Esta codificación se muestra en el ejemplo siguiente.

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [-doc (opciones del compilador de C#)](../../language-reference/compiler-options/doc-compiler-option.md)
- [Comentarios de documentación XML](./index.md)
