---
title: Generación y compilación de código fuente dinámico
ms.date: 03/30/2017
helpviewer_keywords:
- Code Document Object Model
- System.CodeDom namespace
- language-independent source code modeling
- CodeDOM
- multiple languages supported by CodeDOM
- source code in multiple languages
- languages, multiple language support by CodeDOM
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
ms.openlocfilehash: 7379bac07de9b78369d3742fa3288f6fea6a573f
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/29/2019
ms.locfileid: "75544988"
---
# <a name="compile-and-generate-dynamic-source-code"></a>Compilar y generar código fuente dinámico

.NET Framework incluye un mecanismo denominado Code Document Object Model (CodeDOM) que permite que los desarrolladores de programas que emiten código de origen generen código fuente en varios lenguajes de programación en tiempo de ejecución, en función de un único modelo que representa el código que se va a representar.  
  
Para representar el código fuente, los elementos CodeDOM se enlazan entre sí para formar una estructura de datos denominada gráfico CodeDOM, que modela la estructura de parte del código fuente.  
  
El espacio de nombres <xref:System.CodeDom?displayProperty=fullName> define los tipos que pueden representar la estructura lógica del código fuente, independientemente de un lenguaje de programación específico. El espacio de nombres <xref:System.CodeDom.Compiler?displayProperty=fullName> define los tipos para generar código fuente a partir de gráficos CodeDOM y para administrar la compilación del código fuente en los lenguajes admitidos. Los desarrolladores o proveedores de compiladores pueden extender el conjunto de lenguajes admitidos.  
  
El modelado de código fuente independiente del lenguaje puede resultar valioso cuando un programa necesita generar código fuente para un modelo de programa en varios lenguajes o para un lenguaje de destino indeterminado. Por ejemplo, algunos diseñadores usan CodeDOM como una interfaz de abstracción del lenguaje para generar código fuente en el lenguaje de programación correcto, si CodeDOM es compatible con el idioma.  
  
.NET Framework incluye los generadores de código y compiladores de código para <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider> y <xref:Microsoft.VisualBasic.VBCodeProvider>.  
  
## <a name="in-this-section"></a>En esta sección

- [Usar CodeDOM](using-the-codedom.md)

  Describe los usos comunes y muestra cómo se compila un gráfico de objetos simple mediante CodeDOM.  
  
- [Generar código fuente y compilar un programa a partir de un gráfico CodeDOM](generating-and-compiling-source-code-from-a-codedom-graph.md)  

  Describe cómo generar código fuente y compilar el código generado con un compilador externo mediante el uso de las clases definidas en el espacio de nombres `System.CodeDom.Compiler`.  
  
- [Cómo: Crear un archivo de documentación XML mediante CodeDOM](how-to-create-an-xml-documentation-file-using-codedom.md)  

  Describe cómo usar CodeDOM para generar código con comentarios de documentación XML y compilar el código generado para que cree la salida de documentación XML.  
  
- [Cómo: Crear un clase mediante CodeDOM](how-to-create-a-class-using-codedom.md)  

  Describe cómo usar CodeDOM para generar una clase que contenga campos, propiedades, un método, un constructor y un punto de entrada.  
  
## <a name="reference"></a>Referencia  

- <xref:System.CodeDom>  

  Define los elementos que representan elementos de código en lenguajes de programación que tienen como destino Common Language Runtime.  
  
- <xref:System.CodeDom.Compiler>  

  Define las interfaces para generar y compilar código en tiempo de ejecución.  
  
## <a name="related-sections"></a>Secciones relacionadas  

- La [referencia rápida de CodeDom](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)) proporciona una forma rápida para que los desarrolladores busquen los elementos CodeDom que representan elementos de código fuente.
