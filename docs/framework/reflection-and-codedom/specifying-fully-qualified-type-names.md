---
title: Especificar nombres de tipo completos
description: Para la entrada válida para las operaciones de reflexión, use nombres de tipo completos, que tienen especificaciones de nombre de ensamblado, especificaciones de espacio de nombres y nombres de tipo.
ms.date: 02/21/2019
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- reflection, fully qualified type names
- names [.NET Framework], assemblies
- tokens
- BNF
- assemblies [.NET Framework], names
- languages, grammar
- fully qualified type names
- type names
- special characters
- IDENTIFIER
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
ms.openlocfilehash: ff33b6abd31a82c6b80aa794564c5c48648cde63
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865234"
---
# <a name="specifying-fully-qualified-type-names"></a>Especificar nombres de tipo completos

Debe especificar nombres de tipo para tener entradas válidas en varias operaciones de reflexión. Un nombre de tipo completo consiste en una especificación de nombre de ensamblado, una especificación de espacio de nombres y un nombre de tipo. Las especificaciones de nombre de tipo las usan métodos como <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> y <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.

## <a name="grammar-for-type-names"></a>Gramática de los nombres de tipo

 La gramática define la sintaxis de los lenguajes formales. En la tabla siguiente se muestran las reglas léxicas que describen cómo reconocer una entrada válida. Los terminales (es decir, los elementos que no se pueden reducir más) se muestran en mayúsculas. Los no terminales (es decir, los elementos que se pueden reducir más) se muestran en cadenas con mayúsculas y minúsculas mezcladas o en cadenas entre comillas simples, pero la comilla simple (') no forma parte de la sintaxis en sí. El carácter de canalización (&#124;) indica las reglas que tienen subreglas.

<!-- markdownlint-disable MD010 -->
```antlr
TypeSpec
    : ReferenceTypeSpec
    | SimpleTypeSpec
    ;

ReferenceTypeSpec
    : SimpleTypeSpec '&'
    ;

SimpleTypeSpec
    : PointerTypeSpec
    | GenericTypeSpec
    | TypeName
    ;

GenericTypeSpec
   : SimpleTypeSpec ` NUMBER

PointerTypeSpec
    : SimpleTypeSpec '*'
    ;

ArrayTypeSpec
    : SimpleTypeSpec '[ReflectionDimension]'
    | SimpleTypeSpec '[ReflectionEmitDimension]'
    ;

ReflectionDimension
    : '*'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

ReflectionEmitDimension
    : '*'
    | Number '..' Number
    | Number '…'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

Number
    : [0-9]+
    ;

TypeName
    : NamespaceTypeName
    | NamespaceTypeName ',' AssemblyNameSpec
    ;

NamespaceTypeName
    : NestedTypeName
    | NamespaceSpec '.' NestedTypeName
    ;

NestedTypeName
    : IDENTIFIER
    | NestedTypeName '+' IDENTIFIER
    ;

NamespaceSpec
    : IDENTIFIER
    | NamespaceSpec '.' IDENTIFIER
    ;

AssemblyNameSpec
    : IDENTIFIER
    | IDENTIFIER ',' AssemblyProperties
    ;

AssemblyProperties
    : AssemblyProperty
    | AssemblyProperties ',' AssemblyProperty
    ;

AssemblyProperty
    : AssemblyPropertyName '=' AssemblyPropertyValue
    ;
```
<!-- markdownlint-enable MD010 -->

## <a name="specifying-special-characters"></a>Especificación de caracteres especiales

En un nombre de tipo, IDENTIFIER es cualquier nombre válido determinado por las reglas de un lenguaje.

Use la barra diagonal inversa (\\) como carácter de escape para separar los tokens siguientes cuando se usan como parte de IDENTIFIER.

|Token|Significado|
|-----------|-------------|
|\\,|Separador de ensamblados.|
|\\+|Separador de tipos anidados.|
|\\&|Tipo de referencia.|
|\\*|Tipo de puntero.|
|\\[|Delimitador de dimensión de matriz.|
|\\]|Delimitador de dimensión de matriz.|
|\\.|Use la barra diagonal inversa delante de un punto únicamente si el punto se usa en una especificación de matriz. Los puntos de NamespaceSpec no llevan barra diagonal inversa.|
|\\\|Barra diagonal inversa cuando es necesaria como cadena literal.|

Tenga en cuenta que los espacios son relevantes en todos los componentes de TypeSpec, salvo en AssemblyNameSpec. En AssemblyNameSpec, los espacios delante del separador "," son relevantes, pero los espacios detrás del separador "," se omiten.

Las clases de reflexión, como <xref:System.Type.FullName%2A?displayProperty=nameWithType>, devuelven el nombre alterado para que el nombre devuelto pueda usarse en una llamada a <xref:System.Type.GetType%2A>, como en `MyType.GetType(myType.FullName)`.

Por ejemplo, el nombre completo de un tipo podría ser `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.

Si el espacio de nombres fuera `Ozzy.Out+Back`, el signo más debería ir precedido de una barra diagonal inversa. De lo contrario, el analizador lo interpretaría como un separador de anidamiento. La reflexión emite esta cadena como `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.

## <a name="specifying-assembly-names"></a>Especificación de nombres de ensamblado

La información mínima necesaria en una especificación de nombre de ensamblado es el nombre textual (IDENTIFIER) del ensamblado. Puede seguir el IDENTIFIER mediante una lista separada por comas de pares de propiedad-valor, como se describe en la tabla siguiente. La nomenclatura de IDENTIFIER debe seguir las reglas de la nomenclatura de archivos. IDENTIFIER no distingue mayúsculas de minúsculas.

|Nombre de la propiedad|Descripción|Valores permitidos|
|-------------------|-----------------|----------------------|
|**Versión**|Número de versión del ensamblado|*Major.Minor.Build.Revision*, donde *Major*, *Minor*, *Build* y *Revision* son números enteros entre 0 y 65535, ambos incluidos.|
|**PublicKey**|Clave pública completa|Valor de cadena de la clave pública completa en formato hexadecimal. Especifique una referencia nula (**Nothing** en Visual Basic) para indicar explícitamente un ensamblado privado.|
|**PublicKeyToken**|Token de clave pública (hash de 8 bytes de la clave pública completa)|Valor de cadena del token de clave pública en formato hexadecimal. Especifique una referencia nula (**Nothing** en Visual Basic) para indicar explícitamente un ensamblado privado.|
|**Referencia cultural**|Referencia cultural del ensamblado|Referencia cultural del ensamblado en formato RFC-1766, o "neutral" para los ensamblados independientes del lenguaje (no satélite).|
|**Custom**|Objeto binario grande personalizado (BLOB). Actualmente esto solo se usa en los ensamblados generados por el [Generador de imágenes nativas (Ngen)](../tools/ngen-exe-native-image-generator.md).|Cadena personalizada que la herramienta Generador de imágenes nativas usa para notificar a la caché de ensamblados que el ensamblado que se está instalando es una imagen nativa y, por tanto, se tiene que instalar en la caché de imágenes nativas. También se denomina cadena ZAP.|

En el ejemplo siguiente se muestra un **AssemblyName** para un ensamblado de nombre simple con una referencia cultural predeterminada.

```csharp
com.microsoft.crypto, Culture=""
```

En el ejemplo siguiente se muestra una referencia completa para un ensamblado con nombre seguro con la referencia cultural "en".

```csharp
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

En los ejemplos siguientes se muestra un **AssemblyName** parcialmente especificado, que se puede resolver mediante un ensamblado con un nombre simple o seguro.

```csharp
com.microsoft.crypto
com.microsoft.crypto, Culture=""
com.microsoft.crypto, Culture=en
```

En los ejemplos siguientes se muestra un **AssemblyName** parcialmente especificado, que se debe resolver mediante un ensamblado con un nombre simple.

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=null
com.microsoft.crypto, Culture=en, PublicKeyToken=null
```

En los ejemplos siguientes se muestra un **AssemblyName** parcialmente especificado, que se debe resolver mediante un ensamblado con un nombre seguro.

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

## <a name="specifying-generic-types"></a>Especificación de tipos genéricos

SimpleTypeSpec\`NUMBER representa un tipo genérico abierto de 1 a *n* parámetros de tipo genérico. Por ejemplo, para obtener la referencia al tipo genérico abierto List\<T> o al tipo genérico cerrado List\<String>, use ``Type.GetType("System.Collections.Generic.List`1")``; para obtener una referencia al tipo genérico Dictionary\<TKey,TValue>, use ``Type.GetType("System.Collections.Generic.Dictionary`2")``.

## <a name="specifying-pointers"></a>Especificación de punteros

SimpleTypeSpec* representa un puntero no administrado. Por ejemplo, para obtener un puntero al tipo MyType, use `Type.GetType("MyType*")`. Para obtener un puntero a un puntero al tipo MyType, use `Type.GetType("MyType**")`.

## <a name="specifying-references"></a>Especificación de referencias

SimpleTypeSpec & representa un puntero administrado o referencia. Por ejemplo, para obtener una referencia al tipo MyType, use `Type.GetType("MyType &")`. Tenga en cuenta que, a diferencia de los punteros, las referencias están limitadas a un nivel.

## <a name="specifying-arrays"></a>Especificación de matrices

En la gramática de BNF, ReflectionEmitDimension solo se aplica a las definiciones de tipo incompletas recuperadas mediante <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>. Las definiciones de tipo incompletas son objetos <xref:System.Reflection.Emit.TypeBuilder> construidos mediante <xref:System.Reflection.Emit?displayProperty=nameWithType>, pero en los que no se ha llamado a <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType>. Se puede usar ReflectionDimension para recuperar cualquier definición de tipo que se haya completado, es decir, un tipo que se haya cargado.

Para obtener acceso a las matrices en la reflexión, se debe especificar el rango de la matriz:

- `Type.GetType("MyArray[]")` obtiene una matriz unidimensional con límite inferior 0.

- `Type.GetType("MyArray[*]")` obtiene una matriz unidimensional con límite inferior desconocido.
- `Type.GetType("MyArray[][]")` obtiene una matriz de la matriz bidimensional.

- `Type.GetType("MyArray[*,*]")` y `Type.GetType("MyArray[,]")` obtienen una matriz bidimensional rectangular con límites inferiores desconocidos.

Tenga en cuenta que, desde el punto de vista del tiempo de ejecución, `MyArray[] != MyArray[*]`, pero en el caso de las matrices multidimensionales, las dos notaciones son equivalentes. Es decir, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` se evalúa como **true**.

Para **ModuleBuilder.GetType**, `MyArray[0..5]` indica una matriz unidimensional de tamaño 6 y límite inferior 0. `MyArray[4…]` indica una matriz unidimensional de tamaño desconocido y límite inferior 4.

## <a name="see-also"></a>Vea también

- <xref:System.Reflection.AssemblyName>
- <xref:System.Reflection.Emit.ModuleBuilder>
- <xref:System.Reflection.Emit.TypeBuilder>
- <xref:System.Type.FullName%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>
- [Ver información tipos](viewing-type-information.md)
