---
title: Usar el modelo de sintaxis del SDK de .NET Compiler Platform
description: En este tema se proporciona una descripción de los tipos que se usan para entender y manipular nodos de sintaxis.
ms.date: 10/15/2017
ms.custom: mvc
ms.openlocfilehash: fc1b1f5ae5ec985425c8d6aec49ef7f830ea9162
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740473"
---
# <a name="work-with-syntax"></a>Trabajar con sintaxis

El **árbol de sintaxis** es una estructura de datos fundamental expuesta por las API del compilador. Estos árboles representan la estructura léxica y sintáctica del código fuente. Tienen dos importantes finalidades:

1. Permitir herramientas, como un IDE, complementos, herramientas de análisis de código y refactorizaciones, para ver y procesar la estructura sintáctica del código fuente del proyecto de un usuario.
2. Habilitar herramientas, como refactorizaciones y un IDE, para crear, modificar y reorganizar el código fuente de forma natural sin tener que usar ediciones de texto directas. Al crear y manipular árboles, las herramientas pueden crear y reorganizar fácilmente el código fuente.

## <a name="syntax-trees"></a>Árboles de sintaxis

Los árboles de sintaxis son la estructura principal usada para la compilación, el análisis de código, los enlaces, la refactorización, las características de IDE y la generación de código. Ninguna parte del código fuente se entiende sin que primero se haya identificado y clasificado en alguno de los elementos de lenguaje estructural conocidos.

Los árboles de sintaxis tienen tres atributos clave. El primer atributo es que los árboles de sintaxis contienen toda la información de origen con plena fidelidad. Esto significa que el árbol de sintaxis contiene cada fragmento de información del texto de origen, cada construcción gramatical, cada token léxico y todo lo demás, incluidos los espacios en blanco, los comentarios y las directivas de preprocesador. Por ejemplo, cada literal mencionado en el origen se representa exactamente como se ha escrito. Los árboles de sintaxis también representan errores del código fuente cuando el programa está incompleto o tiene un formato incorrecto mediante la representación de tokens omitidos o que faltan en el árbol de sintaxis.

Esto habilita el segundo atributo de los árboles de sintaxis. Un árbol de sintaxis obtenido del analizador puede generar el texto exacto a partir del que se ha analizado. Es posible obtener la representación de texto del subárbol cuya raíz está en ese nodo desde cualquier nodo de sintaxis. Esto significa que los árboles de sintaxis se pueden usar como una manera de crear y editar texto de origen. Al crear un árbol, implícitamente se ha creado el texto equivalente, mientras que al editar un árbol de sintaxis o crear uno nuevo a partir de los cambios en uno existente, se ha editado realmente el texto.

El tercer atributo de los árboles de sintaxis es que son inmutables y seguros para subprocesos.  Esto significa que una vez obtenido un árbol, es una instantánea del estado actual del código y nunca cambia. Esto permite que varios usuarios interactúen con el mismo árbol de sintaxis a la vez en distintos subprocesos sin que se produzca ningún bloqueo ni duplicación. Dado que los árboles son inmutables y no permiten ninguna modificación directa, los métodos de fábrica ayudan a crear y modificar los árboles de sintaxis mediante la creación de instantáneas adicionales del árbol. Los árboles son eficaces en su forma de volver a usar nodos subyacentes, así que es posible volver a crear una nueva versión rápidamente y con poca memoria adicional.

Un árbol de sintaxis es literalmente una estructura de datos de árbol donde los elementos estructurales no terminales son primarios con respecto a otros elementos. Cada árbol de sintaxis se compone de nodos, tokens y curiosidades.

## <a name="syntax-nodes"></a>Nodos de sintaxis

Los nodos de sintaxis son uno de los elementos principales de los árboles de sintaxis. Estos nodos representan construcciones sintácticas como declaraciones, instrucciones, cláusulas y expresiones. Cada categoría de nodos de sintaxis se representa mediante una clase independiente derivada de <xref:Microsoft.CodeAnalysis.SyntaxNode?displayProperty=nameWithType>. El conjunto de clases de nodos no es extensible.

Todos los nodos de sintaxis son nodos no terminales del árbol de sintaxis, lo que significa que siempre tienen otros nodos y tokens como elementos secundarios. Como elemento secundario de otro nodo, cada nodo tiene un nodo principal al que se puede acceder mediante la propiedad <xref:Microsoft.CodeAnalysis.SyntaxNode.Parent?displayProperty=nameWithType>. Dado que los nodos y los árboles son inmutables, el elemento principal de un nodo nunca cambia. La raíz del árbol tiene un elemento principal nulo.

Cada nodo tiene un método <xref:Microsoft.CodeAnalysis.SyntaxNode.ChildNodes?displayProperty=nameWithType> que devuelve una lista de nodos secundarios en orden secuencial según su posición en el texto de origen. Esta lista no contiene tokens. Cada nodo también tiene métodos para examinar descendientes, como <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantNodes%2A>, <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantTokens%2A> o <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantTrivia%2A>, que representan una lista de todos los nodos, tokens o curiosidades que existen en el subárbol cuya raíz está en ese nodo.

Además, cada subclase de nodos de sintaxis expone los mismos elementos secundarios mediante propiedades fuertemente tipadas. Por ejemplo, una clase de nodos <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax> tiene tres propiedades adicionales específicas de los operadores binarios: <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.Left>, <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.OperatorToken> y <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.Right>. El tipo de <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.Left> y <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.Right> es <xref:Microsoft.CodeAnalysis.CSharp.Syntax.ExpressionSyntax>, y el tipo de <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.OperatorToken> es <xref:Microsoft.CodeAnalysis.SyntaxToken>.

Algunos nodos de sintaxis tienen elementos secundarios opcionales. Por ejemplo, <xref:Microsoft.CodeAnalysis.CSharp.Syntax.IfStatementSyntax> tiene un elemento opcional <xref:Microsoft.CodeAnalysis.CSharp.Syntax.ElseClauseSyntax>. Si el elemento secundario no está presente, la propiedad devuelve null.

## <a name="syntax-tokens"></a>Tokens de sintaxis

Los tokens de sintaxis son los terminales de la gramática del lenguaje y representan los fragmentos sintácticos más pequeños del código. Nunca son elementos principales de otros nodos o tokens. Los tokens de sintaxis constan de palabras clave, identificadores, literales y signos de puntuación.

Por eficacia, el tipo <xref:Microsoft.CodeAnalysis.SyntaxToken> es un tipo de valor CLR. Por tanto, a diferencia de los nodos de sintaxis, solo hay una estructura para todos los tipos de tokens con una mezcla de propiedades que tienen significado según el tipo de token que se va a representar.

Por ejemplo, un token de literal entero representa un valor numérico. Además del texto de origen sin formato que abarca el token, el token de literal tiene una propiedad <xref:Microsoft.CodeAnalysis.SyntaxToken.Value> que indica el valor entero descodificado exacto. El tipo de esta propiedad se considera <xref:System.Object>, ya que puede ser alguno de los tipos primitivos.

La propiedad <xref:Microsoft.CodeAnalysis.SyntaxToken.ValueText> transmite la misma información que la propiedad <xref:Microsoft.CodeAnalysis.SyntaxToken.Value>; pero el tipo de esta propiedad siempre es <xref:System.String>. Un identificador en el texto de origen C# puede incluir caracteres de escape Unicode, aunque la sintaxis de la propia secuencia de escape no se considera parte del nombre del identificador. Por tanto, aunque el texto sin formato que abarca el token incluye la secuencia de escape, la propiedad <xref:Microsoft.CodeAnalysis.SyntaxToken.ValueText> no. En su lugar, incluye los caracteres Unicode que identifica el escape. Por ejemplo, si el texto de origen contiene un identificador escrito como `\u03C0`, la propiedad <xref:Microsoft.CodeAnalysis.SyntaxToken.ValueText> de este token devuelve `π`.

## <a name="syntax-trivia"></a>Curiosidades de sintaxis

Las curiosidades de sintaxis representan las partes del texto de origen que no son realmente significativas para la correcta comprensión del código, como los espacios en blanco, los comentarios y las directivas de preprocesador. Al igual que los tokens de sintaxis, las curiosidades son tipos de valor. Se usa el tipo único <xref:Microsoft.CodeAnalysis.SyntaxTrivia?displayProperty=nameWithType> para describir todos los tipos de curiosidades.

Dado que las curiosidades no forman parte de la sintaxis normal del lenguaje y pueden aparecer en cualquier lugar entre dos tokens, no se incluyen en el árbol de sintaxis como elemento secundario de un nodo. Pero dado que son importantes a la hora de implementar una característica como la refactorización y de mantener la plena fidelidad con el texto de origen, existen como parte del árbol de sintaxis.

Puede acceder a las curiosidades si inspecciona las colecciones <xref:Microsoft.CodeAnalysis.SyntaxToken.LeadingTrivia?displayProperty=nameWithType> o <xref:Microsoft.CodeAnalysis.SyntaxToken.TrailingTrivia?displayProperty=nameWithType> de un token. Cuando se analiza el texto de origen, las secuencias de curiosidades se asocian a los tokens. En general, un token es propietario de cualquier curiosidad que le preceda en la misma línea hasta el siguiente token. Cualquier curiosidad situada después de esa línea se asocia al token siguiente. El primer token del archivo de origen obtiene todas las curiosidades iniciales, mientras que la última secuencia de curiosidades del archivo se agrega al último token del archivo, que, de lo contrario, tiene ancho de cero.

A diferencia de los nodos y los tokens de sintaxis, las curiosidades de sintaxis no tienen elementos principales. Pero, dado que forman parte del árbol y cada una está asociada a un token único, se puede acceder al token con el que está asociada mediante la propiedad <xref:Microsoft.CodeAnalysis.SyntaxTrivia.Token?displayProperty=nameWithType>.

## <a name="spans"></a>Intervalos

Cada nodo, token o curiosidad conoce su posición dentro del texto de origen y el número de caracteres del que se compone. Una posición de texto se representa como un entero de 32 bits, que es un índice `char` de base cero. Un objeto <xref:Microsoft.CodeAnalysis.Text.TextSpan> es la posición inicial y un recuento de caracteres, ambos representados como enteros. Si <xref:Microsoft.CodeAnalysis.Text.TextSpan> tiene una longitud cero, hace referencia a una ubicación entre dos caracteres.

Cada nodo tiene dos propiedades <xref:Microsoft.CodeAnalysis.Text.TextSpan>: <xref:Microsoft.CodeAnalysis.SyntaxNode.Span%2A> y <xref:Microsoft.CodeAnalysis.SyntaxNode.FullSpan%2A>.

La propiedad <xref:Microsoft.CodeAnalysis.SyntaxNode.Span%2A> es el intervalo de texto desde el principio del primer token del subárbol del nodo al final del último token. Este intervalo no incluye ninguna curiosidad inicial ni final.

La propiedad <xref:Microsoft.CodeAnalysis.SyntaxNode.FullSpan%2A> es el intervalo de texto que incluye el intervalo normal del nodo, así como el intervalo de cualquier curiosidad inicial o final.

Por ejemplo:

``` csharp
      if (x > 3)
      {
||        // this is bad
          |throw new Exception("Not right.");|  // better exception?||
      }
```

El nodo de la instrucción dentro del bloque tiene un intervalo indicado por las plecas (|). Incluye los caracteres `throw new Exception("Not right.");`. Las plecas dobles (||) indican el intervalo completo. Incluye los mismos caracteres que el intervalo y los caracteres asociados a las curiosidades inicial y final.

## <a name="kinds"></a>Tipos

Cada nodo, token o curiosidad tiene una propiedad <xref:Microsoft.CodeAnalysis.SyntaxNode.RawKind?displayProperty=nameWithType>, de tipo <xref:System.Int32?displayProperty=nameWithType>, que identifica el elemento de sintaxis exacto representado. Este valor se puede convertir en una enumeración específica del lenguaje. Cada lenguaje, C# o Visual Basic, tiene una sola enumeración `SyntaxKind` (<xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind?displayProperty=nameWithType> y <xref:Microsoft.CodeAnalysis.VisualBasic.SyntaxKind?displayProperty=nameWithType>, respectivamente) que enumera todos los posibles nodos, tokens y curiosidades de la gramática. Dicha conversión se puede realizar automáticamente. Para ello, es necesario acceder a los métodos de extensión <xref:Microsoft.CodeAnalysis.CSharp.CSharpExtensions.Kind%2A?displayProperty=nameWithType> o <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicExtensions.Kind%2A?displayProperty=nameWithType>.

La propiedad <xref:Microsoft.CodeAnalysis.SyntaxToken.RawKind> permite anular fácilmente la ambigüedad de los tipos de nodos de sintaxis que comparten la misma clase de nodos. En el caso de los tokens y las curiosidades, esta propiedad es la única manera de distinguir un tipo de elemento de otro.

Por ejemplo, una sola clase <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax> tiene <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.Left>, <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.OperatorToken> y <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.Right> como elementos secundarios. La propiedad <xref:Microsoft.CodeAnalysis.CSharp.CSharpExtensions.Kind%2A> distingue si es un tipo <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.AddExpression>, <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.SubtractExpression> o <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.MultiplyExpression> de nodo de sintaxis.

## <a name="errors"></a>Errores

Aunque el texto de origen contenga errores de sintaxis, se expone un árbol de sintaxis completo con recorrido de ida y vuelta al origen. Si el analizador detecta código que no se ajusta a la sintaxis definida del lenguaje, usa una de estas dos técnicas para crear un árbol de sintaxis.

En primer lugar, si el analizador espera un determinado tipo de token pero no lo encuentra, puede insertar un token que falta en el árbol de sintaxis en la ubicación esperada del token. Un token que falta representa el token real esperado, aunque tiene un intervalo vacío y su propiedad <xref:Microsoft.CodeAnalysis.SyntaxNode.IsMissing?displayProperty=nameWithType> devuelve `true`.

En segundo lugar, el analizador puede omitir tokens hasta encontrar uno en el que pueda seguir analizando. En este caso, los tokens omitidos se adjuntan como un nodo de curiosidades con el tipo <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.SkippedTokensTrivia>.
