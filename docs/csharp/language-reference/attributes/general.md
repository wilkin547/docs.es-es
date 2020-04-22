---
title: 'Atributos reservados de C#: Conditional, Obsolete, AttributeUsage'
ms.date: 04/09/2020
description: El compilador interpreta estos atributos para que afecten al código generado por el compilador.
ms.openlocfilehash: ca3b76387de2a57380d6eb0848991d979a558662
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389821"
---
# <a name="reserved-attributes-conditionalattribute-obsoleteattribute-attributeusageattribute"></a>Atributos reservados: ConditionalAttribute, ObsoleteAttribute, AttributeUsageAttribute

Estos atributos se pueden aplicar a los elementos del código. Agregan significado semántico a esos elementos. El compilador usa esos significados semánticos para modificar su salida e informar de los posibles errores por parte de los desarrolladores que usan el código.

## <a name="conditional-attribute"></a>Atributo `Conditional`

El atributo `Conditional` hace que la ejecución de un método dependa de un identificador de preprocesamiento. El atributo `Conditional` es un alias de <xref:System.Diagnostics.ConditionalAttribute> y se puede aplicar a un método o a una clase de atributo.

En el ejemplo siguiente, `Conditional` se aplica a un método para habilitar o deshabilitar la representación de información de diagnóstico específica del programa:

::::::code language="csharp" source="snippets/trace.cs" interactive="try-dotnet" :::

Si no se define el identificador `TRACE_ON`, no se muestra el resultado del seguimiento. Explore por sí mismo en la ventana interactiva.

El atributo `Conditional` se suele usar con el identificador `DEBUG` para habilitar las funciones de seguimiento y de registro para las compilaciones de depuración, pero no en las compilaciones de versión, como se muestra en el ejemplo siguiente:

::::::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditional" :::

Al llamar a un método marcado como condicional, la presencia o ausencia del símbolo de preprocesamiento especificado determina si se incluye o se omite la llamada. Si el símbolo está definido, se incluye la llamada; de lo contrario, se omite la llamada. Un método condicional debe ser un método de una declaración de clase o estructura, y no debe tener un tipo de valor devuelto `void`. El uso de `Conditional` resulta más limpio y elegante, y menos propenso a generar errores que incluir los métodos dentro de bloques `#if…#endif`.

Si un método tiene varios atributos `Conditional`, se incluye una llamada al método si se define uno o más símbolos condicionales (los símbolos se vinculan de manera lógica entre sí mediante el operador OR). En el ejemplo siguiente, la presencia de `A` o `B` da como resultado una llamada al método:

::::::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetMultipleConditions" :::

### <a name="using-conditional-with-attribute-classes"></a>Uso de `Conditional` con clases de atributos

El atributo `Conditional` también se puede aplicar a una definición de clase de atributo. En el ejemplo siguiente, el atributo personalizado `Documentation` solo agregará información a los metadatos si se define `DEBUG`.

::::::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditionalConditionalAttribute" :::

## <a name="obsolete-attribute"></a>Atributo `Obsolete`

El atributo `Obsolete` marca un elemento de código como ya no recomendado para su uso. El uso de una entidad marcada como obsoleta genera una advertencia o un error. El atributo `Obsolete` es un atributo de uso único y se puede aplicar a cualquier entidad que admita atributos. `Obsolete` es un alias de <xref:System.ObsoleteAttribute>.

En el ejemplo siguiente, el atributo `Obsolete` se aplica a la clase `A` y al método `B.OldMethod`. Dado que el segundo argumento del constructor de atributos aplicado a `B.OldMethod` está establecido en `true`, este método producirá un error del compilador, mientras que, si se usa la clase `A`, solo se generará una advertencia. En cambio, si se llama a `B.NewMethod`, no se generará ninguna advertencia o error. Por ejemplo, al usarla con las definiciones anteriores, el código siguiente genera dos advertencias y un error:

::::::code language="csharp" source="snippets/ObsoleteExample.cs" interactive="try-dotnet" :::

La cadena proporcionada como primer argumento al constructor del atributo se mostrará como parte de la advertencia o el error. Se generan dos advertencias para la clase `A`: una para la declaración de la referencia de clase y otra para el constructor de clases. El atributo `Obsolete` se puede usar sin argumentos, pero se recomienda incluir una explicación de qué se debe usar en su lugar.

## <a name="attributeusage-attribute"></a>Atributo `AttributeUsage`

El atributo `AttributeUsage` determina cómo se puede usar una clase de atributo personalizado. <xref:System.AttributeUsageAttribute> es un atributo que se aplica a las definiciones de atributo personalizado. El atributo `AttributeUsage` permite controlar lo siguiente:

- Los atributos de elementos de programa que se pueden aplicar. A menos que el uso esté restringido, un atributo se puede aplicar a cualquiera de los siguientes elementos de programa:
  - ensamblado
  - module
  - campo
  - event
  - método
  - param
  - propiedad
  - return
  - type
- Si un atributo se puede aplicar a un mismo elemento de programa varias veces.
- Si las clases derivadas heredan atributos.

La configuración predeterminada se parece al siguiente ejemplo cuando se aplica explícitamente:

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageFirst" :::

En este ejemplo, la clase `NewAttribute` se puede aplicar a cualquier elemento de programación compatible, pero solamente se puede aplicar una vez a cada entidad. Las clases derivadas heredan el atributo cuando se aplica a una clase base.

Los argumentos <xref:System.AttributeUsageAttribute.AllowMultiple> y <xref:System.AttributeUsageAttribute.Inherited> son opcionales, por lo que el siguiente código tiene el mismo efecto:

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageSecond" :::

El primer argumento <xref:System.AttributeUsageAttribute> debe ser uno o varios elementos de la enumeración <xref:System.AttributeTargets>. Se pueden vincular diversos tipos de destino con el operador OR, como se refleja en el siguiente ejemplo:

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetDefinePropertyAttribute" :::

A partir de C# 7.3, los atributos se pueden aplicar a la propiedad o el campo de respaldo de una propiedad implementada automáticamente. El atributo se aplica a la propiedad, a menos que se indique el especificador `field` en el atributo. Ambos se muestran en el siguiente ejemplo:

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetUsePropertyAttribute" :::

Si el argumento <xref:System.AttributeUsageAttribute.AllowMultiple> es `true`, el atributo resultante se puede aplicar más de una vez a cada una de las entidades, como se muestra en el siguiente ejemplo:

:::code language="csharp" source="snippets/MultiUseAttribute.cs" id="SnippetMultiUse" :::

En este caso, `MultiUseAttribute` se puede aplicar varias veces porque `AllowMultiple` está establecido en `true`. Los dos formatos mostrados para aplicar varios atributos son válidos.

Si <xref:System.AttributeUsageAttribute.Inherited> se establece en `false`, las clases que se derivan de una clase con atributos no heredan el atributo. Por ejemplo:

:::code language="csharp" source="snippets/NonInheritedAttribute.cs" id="SnippetNonInherited" :::

En este caso, `NonInheritedAttribute` no se aplica a `DClass` a través de la herencia.

## <a name="see-also"></a>Vea también

- <xref:System.Attribute>
- <xref:System.Reflection>
- [Atributos](../../../standard/attributes/index.md)
- [Reflexión](../../programming-guide/concepts/reflection.md)
