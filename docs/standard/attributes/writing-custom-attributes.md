---
title: Escribir atributos personalizados
description: Diseñe sus propios atributos personalizados en .NET. Los atributos personalizados son esencialmente clases tradicionales que se derivan directa o indirectamente de System.Attribute.
ms.date: 07/17/2018
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- multiple attribute instances
- AttributeTargets enumeration
- attributes [.NET], custom
- AllowMultiple property
- custom attributes
- AttributeUsageAttribute class, custom attributes
- Inherited property
- attribute classes, declaring
ms.assetid: 97216f69-bde8-49fd-ac40-f18c500ef5dc
ms.openlocfilehash: e3c97f28a05f2e5396872fe808cae0d48d5a4824
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727008"
---
# <a name="writing-custom-attributes"></a>Escribir atributos personalizados

Para diseñar sus propios atributos personalizados, no necesitará dominar muchos conceptos nuevos. Si está familiarizado con la programación orientada a objetos y sabe cómo diseñar clases, ya tiene la mayoría de los conocimientos necesarios. Los atributos personalizados son esencialmente clases tradicionales que se derivan directa o indirectamente de <xref:System.Attribute?displayProperty=nameWithType>. Como sucede con las clases tradicionales, los atributos personalizados contienen métodos que almacenan y recuperan datos.  
  
 Los pasos principales para diseñar correctamente clases de atributos personalizados son los siguientes:  
  
- [Aplicar AttributeUsageAttribute](#applying-the-attributeusageattribute)  
  
- [Declarar la clase de atributo](#declaring-the-attribute-class)  
  
- [Declarar constructores](#declaring-constructors)  
  
- [Declarar propiedades](#declaring-properties)  
  
 En esta sección se describe cada uno de estos pasos y, para finalizar, se muestra un [ejemplo de atributo personalizado](#custom-attribute-example).  
  
## <a name="applying-the-attributeusageattribute"></a>Aplicar AttributeUsageAttribute  

 La declaración de un atributo personalizado empieza con <xref:System.AttributeUsageAttribute?displayProperty=nameWithType>, que define algunas de las características clave de la clase de atributo. Por ejemplo, puede especificar si el atributo lo pueden heredar otras clases o especificar los elementos a los que se puede aplicar el atributo. En el fragmento de código siguiente se muestra cómo usar <xref:System.AttributeUsageAttribute>.  
  
 [!code-cpp[Conceptual.Attributes.Usage#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#5)]
 [!code-csharp[Conceptual.Attributes.Usage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#5)]
 [!code-vb[Conceptual.Attributes.Usage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#5)]  
  
 <xref:System.AttributeUsageAttribute> tiene tres miembros que son importantes para la creación de atributos personalizados: [AttributeTargets](#attributetargets-member), [Inherited](#inherited-property) y [AllowMultiple](#allowmultiple-property).  
  
### <a name="attributetargets-member"></a>Miembro AttributeTargets  

 En el ejemplo anterior, se especifica <xref:System.AttributeTargets.All?displayProperty=nameWithType>, lo que indica que este atributo se puede aplicar a todos los elementos de programa. Como alternativa, puede especificar <xref:System.AttributeTargets.Class?displayProperty=nameWithType>, que indica que el atributo solo se puede aplicar a una clase, o <xref:System.AttributeTargets.Method?displayProperty=nameWithType>, que indica que el atributo solo se puede aplicar a un método. De esta manera, un atributo personalizado puede marcar para descripción todos los elementos del programa.  
  
 También puede pasar varios valores <xref:System.AttributeTargets>. El fragmento de código siguiente especifica que un atributo personalizado se puede aplicar a cualquier clase o método.  
  
 [!code-cpp[Conceptual.Attributes.Usage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#6)]
 [!code-csharp[Conceptual.Attributes.Usage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#6)]
 [!code-vb[Conceptual.Attributes.Usage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#6)]  
  
### <a name="inherited-property"></a>Propiedad Inherited  

 La propiedad <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> indica si el atributo lo pueden heredar clases derivadas de las clases a las que se aplica el atributo. Esta propiedad acepta una marca `true` (valor predeterminado) o `false`. En el ejemplo siguiente, `MyAttribute` tiene un valor <xref:System.AttributeUsageAttribute.Inherited%2A> predeterminado de `true`, mientras que `YourAttribute` tiene un valor <xref:System.AttributeUsageAttribute.Inherited%2A> de `false`.  
  
 [!code-cpp[Conceptual.Attributes.Usage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Attributes.Usage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#7)]
 [!code-vb[Conceptual.Attributes.Usage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#7)]  
  
 Los dos atributos se aplican entonces a un método de la clase base `MyClass`.  
  
 [!code-cpp[Conceptual.Attributes.Usage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#9)]
 [!code-csharp[Conceptual.Attributes.Usage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#9)]
 [!code-vb[Conceptual.Attributes.Usage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#9)]  
  
 Por último, la clase `YourClass` se hereda de la clase base `MyClass`. El método `MyMethod` muestra `MyAttribute`, pero no `YourAttribute`.  
  
 [!code-cpp[Conceptual.Attributes.Usage#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#10)]
 [!code-csharp[Conceptual.Attributes.Usage#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#10)]
 [!code-vb[Conceptual.Attributes.Usage#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#10)]  
  
### <a name="allowmultiple-property"></a>Propiedad AllowMultiple  

 La propiedad <xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=nameWithType> indica si pueden existir varias instancias del atributo en un elemento. Si establece en `true`, se permiten varias instancias; si se establece en `false` (el valor predeterminado), solo se permite una instancia.  
  
 En el ejemplo siguiente, `MyAttribute` tiene un valor <xref:System.AttributeUsageAttribute.AllowMultiple%2A> predeterminado de `false`, mientras que `YourAttribute` tiene un valor de `true`.  
  
 [!code-cpp[Conceptual.Attributes.Usage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#11)]
 [!code-csharp[Conceptual.Attributes.Usage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#11)]
 [!code-vb[Conceptual.Attributes.Usage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#11)]  
  
 Si se aplican varias instancias de estos atributos, `MyAttribute` produce un error del compilador. En el ejemplo de código siguiente se muestra el uso válido de `YourAttribute` y el uso no válido de `MyAttribute`.  
  
 [!code-cpp[Conceptual.Attributes.Usage#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#13)]
 [!code-csharp[Conceptual.Attributes.Usage#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#13)]
 [!code-vb[Conceptual.Attributes.Usage#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#13)]  
  
 Si tanto la propiedad <xref:System.AttributeUsageAttribute.AllowMultiple%2A> como la propiedad <xref:System.AttributeUsageAttribute.Inherited%2A> se establecen en `true`, una clase que se hereda de otra clase puede heredar un atributo y tiene otra instancia del mismo atributo aplicada en la misma clase secundaria. Si se establece <xref:System.AttributeUsageAttribute.AllowMultiple%2A> en `false`, las instancias nuevas del mismo atributo de la clase secundaria sobrescribirán los valores de los atributos de la clase primaria.  
  
## <a name="declaring-the-attribute-class"></a>Declarar la clase de atributo  

 Después de aplicar <xref:System.AttributeUsageAttribute>, puede empezar a definir los detalles del atributo. La declaración de una clase de atributo es similar a la declaración de una clase tradicional, como se muestra en el código siguiente.  
  
 [!code-cpp[Conceptual.Attributes.Usage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#14)]
 [!code-csharp[Conceptual.Attributes.Usage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#14)]
 [!code-vb[Conceptual.Attributes.Usage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#14)]  
  
 En esta definición de atributo se muestra lo siguiente:  
  
- Las clases de atributos se deben declarar como clases públicas.  
  
- Por convención, el nombre de la clase de atributo termina con la palabra **Attribute**. Aunque no es obligatoria, se recomienda seguir esta convención para mejorar la legibilidad. Cuando se aplica el atributo, la inclusión de la palabra Attribute es opcional.  
  
- Todas las clases de atributo deben heredar directa o indirectamente de <xref:System.Attribute?displayProperty=nameWithType>.  
  
- En Microsoft Visual Basic, todas las clases de atributos personalizados deben tener el atributo <xref:System.AttributeUsageAttribute?displayProperty=nameWithType>.  
  
## <a name="declaring-constructors"></a>Declarar constructores  

 Los atributos se inicializan con constructores del mismo modo que las clases tradicionales. En el siguiente fragmento de código se muestra un constructor de atributos típico. Este constructor público acepta un parámetro y establece una variable de miembro igual a su valor.  
  
 [!code-cpp[Conceptual.Attributes.Usage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#15)]
 [!code-csharp[Conceptual.Attributes.Usage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#15)]
 [!code-vb[Conceptual.Attributes.Usage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#15)]  
  
 Puede sobrecargar el constructor para adaptarse a distintas combinaciones de valores. Si también define una [propiedad](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)) para la clase de atributo personalizado, puede utilizar una combinación de parámetros con nombre y de posición al inicializar el atributo. Normalmente, se definen todos los parámetros necesarios como de posición y todos parámetros opcionales como con nombre. En este caso, el atributo no se puede inicializar sin el parámetro obligatorio. Todos los demás parámetros son opcionales. Tenga en cuenta que en Visual Basic, los constructores de una clase de atributo no deben utilizar un argumento ParamArray.  
  
 En el ejemplo de código siguiente, se muestra cómo se puede aplicar un atributo que utiliza el constructor anterior mediante parámetros obligatorios y opcionales. Se supone que el atributo tiene un valor booleano obligatorio y una propiedad de cadena opcional.  
  
 [!code-cpp[Conceptual.Attributes.Usage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#17)]
 [!code-csharp[Conceptual.Attributes.Usage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#17)]
 [!code-vb[Conceptual.Attributes.Usage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#17)]  
  
## <a name="declaring-properties"></a>Declarar propiedades  

 Si quiere definir un parámetro con nombre o proporcionar un método sencillo para devolver los valores almacenados por el atributo, declare una [propiedad](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)). Las propiedades de atributo deben declararse como entidades públicas con una descripción del tipo de datos que se devolverá. Defina la variable que contendrá el valor de la propiedad y asóciela con los métodos **get** y **set** . En el ejemplo de código siguiente se muestra cómo implementar una propiedad simple en el atributo.  
  
 [!code-cpp[Conceptual.Attributes.Usage#16](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#16)]
 [!code-csharp[Conceptual.Attributes.Usage#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#16)]
 [!code-vb[Conceptual.Attributes.Usage#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#16)]  
  
## <a name="custom-attribute-example"></a>ejemplo de atributo personalizado  

 En esta sección se incorpora la información anterior y se muestra cómo se diseña un atributo simple que documente información sobre el autor de una sección del código. El atributo de este ejemplo almacena el nombre y el nivel del programador y si se ha revisado el código. Utiliza tres variables privadas para almacenar los valores reales que se deben guardar. Cada variable se representa mediante una propiedad pública que obtiene y establece los valores. Por último, el constructor se define con dos parámetros obligatorios.  
  
 [!code-cpp[Conceptual.Attributes.Usage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#4)]
 [!code-csharp[Conceptual.Attributes.Usage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#4)]
 [!code-vb[Conceptual.Attributes.Usage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#4)]  
  
 Puede aplicar este atributo con el nombre completo, `DeveloperAttribute`, o el nombre abreviado, `Developer`, de una de las maneras siguientes.  
  
 [!code-cpp[Conceptual.Attributes.Usage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#12)]
 [!code-csharp[Conceptual.Attributes.Usage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#12)]
 [!code-vb[Conceptual.Attributes.Usage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#12)]  
  
 En el primer ejemplo se muestra el atributo aplicado solo con los parámetros con nombre obligatorios, mientras que en el segundo ejemplo se muestra el atributo aplicado con los parámetros obligatorios y opcionales.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Attribute?displayProperty=nameWithType>
- <xref:System.AttributeUsageAttribute?displayProperty=nameWithType>
- [Atributos](index.md)
