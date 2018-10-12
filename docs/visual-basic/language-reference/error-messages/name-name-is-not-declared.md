---
title: Nombre &#39; &lt;nombre&gt; &#39; no se ha declarado
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
author: rpetrusha
ms.author: ronpet
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: 3f950bd5604fae7c7d48f6898a4514053061fe10
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49122812"
---
# <a name="name-39ltnamegt39-is-not-declared"></a>Nombre &#39; &lt;nombre&gt; &#39; no se ha declarado
Una instrucción hace referencia a un elemento de programación, pero el compilador no encuentra un elemento con ese nombre exacto.  
  
 **Identificador de error:** BC30451  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Compruebe que el nombre de la instrucción de referencia esté bien escrito. Visual Basic distingue mayúsculas de minúsculas, pero cualquier otra variación en la ortografía se considera como un nombre completamente distinto. Tenga en cuenta que el carácter de subrayado (`_`) es parte del nombre y, por tanto, parte de la ortografía.  
  
2. Compruebe que tiene el operador de acceso de miembro (`.`) entre un objeto y su miembro. Por ejemplo, si tiene un control <xref:System.Windows.Forms.TextBox> denominado `TextBox1`, para tener acceso a su propiedad <xref:System.Windows.Forms.TextBoxBase.Text%2A> debe escribir `TextBox1.Text`. Si en su lugar escribe `TextBox1Text`, ha creado un nombre diferente.  
  
3. Si es correcta la ortografía y la sintaxis de cualquier acceso a miembros de objeto es correcta, compruebe que se ha declarado el elemento. Para obtener más información, consulte [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).  
  
4. Si se ha declarado el elemento de programación, compruebe que esté dentro del ámbito. Si la instrucción que se hace referencia está fuera de la región que declara el elemento de programación, es posible que deba calificar el nombre del elemento. Para obtener más información, consulta [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).  

5. Si no usa un nombre completo del tipo o nombre de los tipos y miembros (por ejemplo, el código hace referencia a una propiedad como `MethodInfo.Name` en lugar de `System.Reflection.MethodInfo.Name`), agregue un [Imports (instrucción)](../statements/imports-statement-net-namespace-and-type.md).

6. Si intenta compilar un proyecto de estilo SDK (un proyecto con un \*archivo .vbproj que comienza con la línea `<Project Sdk="Microsoft.NET.Sdk">`) y el mensaje de error hace referencia a un tipo o miembro en el ensamblado Microsoft.VisualBasic.dll, configure la aplicación compilar con una referencia a la biblioteca en tiempo de ejecución de Visual Basic. De forma predeterminada, un subconjunto de la biblioteca está incrustado en el ensamblado en un proyecto de estilo SDK.

   Por ejemplo, en el ejemplo siguiente se produce un error al compilarse porque el <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A?displayProperty=fullName> no se encuentra el método. No se incrustan en el subconjunto del tiempo de ejecución de Visual Basic incluido con la aplicación.  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb)]

   Para corregir este error, agregue el `<VBRuntime>Default</VBRuntime>` elemento a los proyectos `<PropertyGroup>` sección, como la siguiente muestra de archivo de proyecto de Visual Basic.

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a>Vea también  

[Resumen de constantes y declaraciones](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
