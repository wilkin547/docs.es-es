---
title: No se ha declarado el nombre '<name>'
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: 76c1ab4fb5f1f8e4c76a06110f4b0f9026cca201
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871545"
---
# <a name="name-name-is-not-declared"></a>No se ha declarado el nombre '\<name>'

Una instrucción hace referencia a un elemento de programación, pero el compilador no puede encontrar un elemento con ese nombre exacto.  
  
 **Identificador de error:** BC30451  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Compruebe que el nombre de la instrucción de referencia esté bien escrito. Visual Basic no distingue entre mayúsculas y minúsculas, pero cualquier otra variación en la ortografía se considera un nombre completamente diferente. Tenga en cuenta que el carácter de subrayado (`_`) es parte del nombre y, por tanto, parte de la ortografía.  
  
2. Compruebe que tiene el operador de acceso a miembros ( `.` ) entre un objeto y su miembro. Por ejemplo, si tiene un control <xref:System.Windows.Forms.TextBox> denominado `TextBox1`, para tener acceso a su propiedad <xref:System.Windows.Forms.TextBoxBase.Text%2A> debe escribir `TextBox1.Text`. Si en su lugar escribe `TextBox1Text`, ha creado un nombre diferente.  
  
3. Si la ortografía es correcta y la sintaxis de cualquier acceso de miembro de objeto es correcta, compruebe que se ha declarado el elemento. Para obtener más información, vea [elementos declarados](../../programming-guide/language-features/declared-elements/index.md).  
  
4. Si se ha declarado el elemento de programación, compruebe que está en el ámbito. Si la instrucción de referencia está fuera de la región que declara el elemento de programación, es posible que deba calificar el nombre del elemento. Para obtener más información, consulta [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).  

5. Si no usa un tipo completo o un nombre de miembro (por ejemplo, el código hace referencia a una propiedad como `MethodInfo.Name` en lugar de `System.Reflection.MethodInfo.Name` ), agregue una [instrucción Imports](../statements/imports-statement-net-namespace-and-type.md).

6. Si intenta compilar un proyecto de estilo SDK (un proyecto con un \* archivo. vbproj que comienza con la línea `<Project Sdk="Microsoft.NET.Sdk">` ) y el mensaje de error hace referencia a un tipo o miembro del ensamblado Microsoft.VisualBasic.dll, configure la aplicación para que se compile con una referencia a la biblioteca en tiempo de ejecución de Visual Basic. De forma predeterminada, un subconjunto de la biblioteca se incrusta en el ensamblado en un proyecto de estilo SDK.

   Por ejemplo, el ejemplo siguiente no se compila porque <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ChangeType%2A?displayProperty=fullName> no se puede encontrar el método. No se incrusta en el subconjunto del tiempo de ejecución de Visual Basic incluido en la aplicación.  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb?highlight=7)]

   Para solucionar este error, agregue el `<VBRuntime>Default</VBRuntime>` elemento a la sección de proyectos `<PropertyGroup>` , como se muestra en el siguiente archivo de proyecto de Visual Basic.

   [!code-xml[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a>Consulte también

- [Resumen de las constantes y declaraciones](../keywords/declarations-and-constants-summary.md)
- [Convenciones de nomenclatura de Visual Basic](../../programming-guide/program-structure/naming-conventions.md)
- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
