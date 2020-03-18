---
title: AttributeUsage (C#)
ms.date: 04/25/2018
ms.openlocfilehash: a3a82e33d7259ec56ec3e907bc3d4d9f8a01167d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "61668723"
---
# <a name="attributeusage-c"></a>AttributeUsage (C#)

Determina cómo se puede usar una clase de atributo personalizado. <xref:System.AttributeUsageAttribute> es un atributo que se aplica a las definiciones de atributo personalizado. El atributo `AttributeUsage` permite controlar lo siguiente:

- Los atributos de elementos de programa que se pueden aplicar. A menos que el uso esté restringido, un atributo se puede aplicar a cualquiera de los siguientes elementos de programa:
  - ensamblado
  - module
  - campo
  - evento
  - método
  - param
  - Propiedad
  - return
  - tipo
- Si un atributo se puede aplicar a un mismo elemento de programa varias veces.
- Si las clases derivadas heredan atributos.

La configuración predeterminada se parece al siguiente ejemplo cuando se aplica explícitamente:

[!code-csharp[Define a new attribute](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#1)]

En este ejemplo, la clase `NewAttribute` se puede aplicar a cualquier elemento de programación compatible, pero solamente se puede aplicar una vez a cada entidad. Las clases derivadas heredan el atributo cuando se aplica a una clase base.

Los argumentos <xref:System.AttributeUsageAttribute.AllowMultiple> y <xref:System.AttributeUsageAttribute.Inherited> son opcionales, por lo que el siguiente código tiene el mismo efecto:

[!code-csharp[Omit optional attributes](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#2)]

El primer argumento <xref:System.AttributeUsageAttribute> debe ser uno o varios elementos de la enumeración <xref:System.AttributeTargets>. Se pueden vincular diversos tipos de destino con el operador OR, como se refleja en el siguiente ejemplo:

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#1)]

A partir de C# 7.3, los atributos se pueden aplicar a la propiedad o el campo de respaldo de una propiedad implementada automáticamente. El atributo se aplica a la propiedad, a menos que se indique el especificador `field` en el atributo. Ambos se muestran en el siguiente ejemplo:

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#2)]

Si el argumento <xref:System.AttributeUsageAttribute.AllowMultiple> es `true`, el atributo resultante se puede aplicar más de una vez a cada una de las entidades, como se muestra en el siguiente ejemplo:

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/MultiUseAttribute.cs#1)]

En este caso, `MultiUseAttribute` se puede aplicar varias veces porque `AllowMultiple` está establecido en `true`. Los dos formatos mostrados para aplicar varios atributos son válidos.

Si <xref:System.AttributeUsageAttribute.Inherited> se establece en `false`, las clases que se derivan de una clase con atributos no heredan el atributo. Por ejemplo:

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/NonInheritedAttribute.cs#1)]

En este caso, `NonInheritedAttribute` no se aplica a `DClass` a través de la herencia.

## <a name="remarks"></a>Comentarios

`AttributeUsage` es un atributo de uso único; no se puede aplicar más de una vez a la misma clase. `AttributeUsage` es un alias de <xref:System.AttributeUsageAttribute>.

Para obtener más información, consulte [Acceder a atributos mediante reflexión (C#)](accessing-attributes-by-using-reflection.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra el efecto de los argumentos <xref:System.AttributeUsageAttribute.Inherited> y <xref:System.AttributeUsageAttribute.AllowMultiple> en el atributo <xref:System.AttributeUsageAttribute> y cómo se pueden enumerar los atributos personalizados aplicados a una clase.

[!code-csharp[Applying and querying attributes](../../../../../samples/snippets/csharp/attributes/Program.cs#1)]

## <a name="sample-output"></a>Resultados del ejemplo

```text
Attributes on Base Class:
FirstAttribute
SecondAttribute
Attributes on Derived Class:
ThirdAttribute
ThirdAttribute
SecondAttribute
```

## <a name="see-also"></a>Vea también

- <xref:System.Attribute>
- <xref:System.Reflection>
- [Guía de programación de C#](../..//index.md)
- [Atributos](../../../..//standard/attributes/index.md)
- [Reflexión (C#)](../reflection.md)
- [Atributos](index.md)
- [Crear atributos personalizados (C#)](creating-custom-attributes.md)
- [Acceder a atributos mediante reflexión (C#)](accessing-attributes-by-using-reflection.md)
