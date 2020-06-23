---
title: Tipos de colección en contratos de datos
description: Obtenga información sobre cómo el modelo de contrato de datos trata las colecciones en el .NET Framework y cómo WCF admite la serialización de datos para los tipos de colección.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- collection types [WCF], data contracts
- data contracts [WCF], collection types
- collection types [WCF]
ms.assetid: 9b45b28e-0a82-4ea3-8c33-ec0094aff9d5
ms.openlocfilehash: 83acf1f74bf3cb117f3f94743eda32d3f2cc4b82
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245185"
---
# <a name="collection-types-in-data-contracts"></a>Tipos de colección en contratos de datos

Una *colección* es una lista de elementos de un determinado tipo. En el .NET Framework, estas listas se pueden representar utilizando matrices o una variedad de otros tipos (lista genérica, genérica <xref:System.ComponentModel.BindingList%601> , <xref:System.Collections.Specialized.StringCollection> o <xref:System.Collections.ArrayList> ). Por ejemplo, una colección puede albergar una lista de direcciones para un determinado cliente. Estas colecciones se denominan *colecciones de lista*, con independencia de cual sea su tipo real.

Existe una forma especial de colección que representa una asociación entre un elemento (la "clave") y otro (el "valor"). En el .NET Framework, se representan mediante tipos como <xref:System.Collections.Hashtable> y el Diccionario genérico. Por ejemplo, una colección de asociaciones puede asignar una ciudad ("clave") a su población ("valor"). Estas colecciones se denominan *colecciones de diccionario*, con independencia de cual sea su tipo real.

Las colecciones reciben un tratamiento especial en el modelo del contrato de datos.

Los tipos que implementan la interfaz <xref:System.Collections.IEnumerable> , incluyendo las matrices y las colecciones genéricas, se reconocen como colecciones. De entre ellos, los tipos que implementan <xref:System.Collections.IDictionary> o las interfaces <xref:System.Collections.Generic.IDictionary%602> genéricas son colecciones de diccionarios; todos los otros son colecciones de listas.

Los requisitos adicionales en los tipos de colección, como tener un método llamado `Add` y un constructor sin parámetros, se describen en detalle en las secciones siguientes. Esto garantiza que los tipos de colección se puedan tanto serializar como deserializar. Esto significa que algunas colecciones no se admiten directamente, como el genérico <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> (porque no tiene ningún constructor sin parámetros). Sin embargo, para información sobre cómo burlar estas restricciones, vea la sección "Utilizar tipos de interfaz de colección y colecciones de solo lectura" a continuación de este tema.

Los tipos contenidos en las colecciones deben ser tipos de contrato de datos o, de lo contrario, se deben poder serializar. Para obtener más información, vea [tipos admitidos por el serializador de contrato de datos](types-supported-by-the-data-contract-serializer.md).

Para obtener más información acerca de qué es y qué no se considera una colección válida, así como sobre cómo se serializan las colecciones, vea la información sobre la serialización de colecciones en la sección "reglas avanzadas de colección" de este tema.

## <a name="interchangeable-collections"></a>Colecciones intercambiables

Se considera que todas las colecciones de listas del mismo tipo tienen el mismo contrato de datos (a menos que se personalicen utilizando el atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> , como se aborda más adelante en este tema). Así, por ejemplo, los contratos de datos siguientes son equivalentes.

[!code-csharp[c_collection_types_in_data_contracts#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#0)]
[!code-vb[c_collection_types_in_data_contracts#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#0)]

Ambos contratos de datos generan XML similar al código siguiente.

```xml
<PurchaseOrder>
    <customerName>...</customerName>
    <items>
        <Item>...</Item>
        <Item>...</Item>
        <Item>...</Item>
        ...
    </items>
    <comments>
        <string>...</string>
        <string>...</string>
        <string>...</string>
        ...
    </comments>
</PurchaseOrder>
```

La intercambiabilidad de colecciones permite utilizar, por ejemplo, un tipo de colección optimizado para rendimiento en el servidor y un tipo de colección diseñado para estar enlazado a los componentes de la interfaz de usuario en el cliente.

De manera similar a las colecciones de listas, se considera que todas las colecciones de diccionarios que tienen la misma clave y tipos de valor tienen el mismo contrato de datos (a menos que se personalicen utilizando el atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> ).

Solo el tipo de contrato de datos importa en lo relativo a la equivalencia de colección, no los tipos .NET. Es decir, una colección de Type1 se considera equivalente a una colección de Type2 si Type1 y Type2 tienen contratos de datos equivalentes.

Se considera que las colecciones no genéricas tienen el mismo contrato de datos que las colecciones genéricas de tipo `Object`. (Por ejemplo, los contratos de datos para <xref:System.Collections.ArrayList> y la <xref:System.Collections.Generic.List%601> genérica de `Object` son los mismos.)

## <a name="using-collection-interface-types-and-read-only-collections"></a>Utilizar tipos de interfaz de colección y colecciones de solo lectura

Los tipos de interfaz de colección (<xref:System.Collections.IEnumerable>, <xref:System.Collections.IDictionary>, <xref:System.Collections.Generic.IDictionary%602>genérico, o interfaces derivadas de estas interfaces) también se considera que tienen contratos de datos de colección, equivalentes a los contratos de datos de colección para los tipos de colección reales. Por lo tanto, es posible declarar el tipo que se está serializando como un tipo de interfaz de colección y los resultados son los mismos que si se hubiese utilizado un tipo de colección real. Por ejemplo, los contratos de datos siguientes son equivalentes.

[!code-csharp[c_collection_types_in_data_contracts#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#1)]
[!code-vb[c_collection_types_in_data_contracts#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#1)]

Durante la serialización, cuando el tipo declarado es una interfaz, el tipo de instancia real que se usa puede ser cualquier tipo que implemente esa interfaz. Las restricciones descritas anteriormente (con un constructor sin parámetros y un `Add` método) no se aplican. Por ejemplo, puede establecer direcciones en Customer2 en una instancia de <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> genérica de dirección, aunque no pueda declarar directamente un miembro de datos de tipo <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>genérica.

Durante la deserialización, cuando el tipo declarado es una interfaz, el motor de serialización elige un tipo que implemente la interfaz declarada y se crea una instancia del tipo. El mecanismo de tipos conocidos (descrito en [tipos conocidos de contratos de datos](data-contract-known-types.md)) no tiene ningún efecto aquí; la elección de tipo está integrada en WCF.

## <a name="customizing-collection-types"></a>Personalizar tipos de colección

Puede personalizar tipos de colección utilizando el atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> , que tiene varios usos.

Observe que al personalizar los tipos de colección se pone en peligro la posibilidad de intercambio de colecciones, por lo que normalmente se recomienda evitar aplicar este atributo siempre que sea posible. Para obtener más información acerca de este problema, consulte la sección "reglas avanzadas de colección" más adelante en este tema.

### <a name="collection-data-contract-naming"></a>Denominación de contrato de datos de colección

Las reglas para denominar los tipos de colección son similares a las existentes para denominar los tipos de contrato de datos normales, como se describe en [Data Contract Names](data-contract-names.md), aunque existen algunas diferencias importantes:

- El atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> se utiliza para personalizar el nombre, en lugar del atributo <xref:System.Runtime.Serialization.DataContractAttribute> . El atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> también tiene propiedades `Name` y `Namespace` .

- Cuando no se aplica el atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> , el nombre predeterminado y el espacio de nombres para los tipos de colección dependen de los nombres y espacios de nombres de tipos contenidos dentro de la colección. No se ven afectados por el nombre ni el espacio de nombres del propio tipo de colección. Para obtener un ejemplo, vea los tipos siguientes.

  ```csharp
  public CustomerList1 : Collection<string> {}
  public StringList1 : Collection<string> {}
  ```

El nombre del contrato de datos de ambos tipos es "ArrayOfstring" y no "CustomerList1" o "StringList1". Esto significa que la serialización de uno de estos tipos en el nivel raíz aporta XML similar al código siguiente.

```xml
<ArrayOfstring>
    <string>...</string>
    <string>...</string>
    <string>...</string>
    ...
</ArrayOfstring>
```

Esta regla de nomenclatura se eligió para garantizar que un tipo no personalizado que represente una lista de cadenas tenga el mismo contrato de datos y la misma representación XML. Esto posibilita la intercambiabilidad de colecciones. En este ejemplo, CustomerList1 y StringList1 son completamente intercambiables.

Sin embargo, cuando se aplica el atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> , la colección se vuelve un contrato de datos de colección personalizado, aunque no se haya establecido ninguna propiedad en el atributo. El nombre y espacio de nombres del contrato de datos de colección dependen del propio tipo de colección. Para ver un ejemplo, vea el tipo siguiente.

[!code-csharp[c_collection_types_in_data_contracts#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#2)]
[!code-vb[c_collection_types_in_data_contracts#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#2)]

Al serializar, el XML resultante es similar al siguiente.

```xml
<CustomerList2>
    <string>...</string>
    <string>...</string>
    <string>...</string>
    ...
</CustomerList2>
```

Tenga en cuenta que ha dejado de ser equivalente a la representación XML de los tipos no personalizados.

- Puede utilizar las propiedades `Name` y `Namespace` para personalizar más la denominación. Vea la siguiente clase.

  [!code-csharp[c_collection_types_in_data_contracts#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#3)]
  [!code-vb[c_collection_types_in_data_contracts#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#3)]

El XML resultante es similar al siguiente.

```xml
<cust_list>
    <string>...</string>
    <string>...</string>
    <string>...</string>
    ...
</cust_list>
```

Para obtener más información, vea la sección "reglas avanzadas de colección" más adelante en este tema.

### <a name="customizing-the-repeating-element-name-in-list-collections"></a>Personalizar el nombre de elementos repetidos en colecciones de listas

Las colecciones de listas contienen entradas repetidas. Normalmente, cada entrada repetida se representa como un elemento denominado según el nombre del contrato de datos del tipo contenido en la colección.

En los ejemplos `CustomerList` , las colecciones contenían cadenas. El nombre del contrato de datos para el tipo primitivo de cadena es "String", por lo que el elemento repetido era " \<string> ".

Sin embargo, utilizando la propiedad <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> en el atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> , se puede personalizar este nombre de elementos repetidos. Para ver un ejemplo, vea el tipo siguiente.

[!code-csharp[c_collection_types_in_data_contracts#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#4)]
[!code-vb[c_collection_types_in_data_contracts#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#4)]

El XML resultante es similar al siguiente.

```xml
<CustomerList4>
    <customer>...</customer>
    <customer>...</customer>
    <customer>...</customer>
    ...
</CustomerList4>
```

El espacio de nombres del elemento repetido es siempre igual al espacio de nombres del contrato de datos de la colección, que se puede personalizar mediante la propiedad `Namespace` , como se comentaba anteriormente.

### <a name="customizing-dictionary-collections"></a>Personalizar las colecciones de diccionarios

Las colecciones de diccionarios son esencialmente listas de entradas, donde cada entrada tiene una clave seguida de un valor. Al igual que sucede con las listas normales, puede cambiar el nombre de elemento que corresponde al elemento repetido mediante la propiedad <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> .

Además, puede cambiar los nombres de elemento que representan la clave y el valor utilizando las propiedades <xref:System.Runtime.Serialization.CollectionDataContractAttribute.KeyName%2A> y <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ValueName%2A> . Los espacios de nombres para estos elementos son los mismos que el espacio de nombres del contrato de datos de colección.

Para ver un ejemplo, vea el tipo siguiente.

[!code-csharp[c_collection_types_in_data_contracts#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#5)]
[!code-vb[c_collection_types_in_data_contracts#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#5)]

Al serializar, el XML resultante es similar al siguiente.

```xml
<CountriesOrRegionsWithCapitals>
    <entry>
        <countryorregion>USA</countryorregion>
        <capital>Washington</capital>
    </entry>
    <entry>
        <countryorregion>France</countryorregion>
        <capital>Paris</capital>
    </entry>
    ...
</CountriesOrRegionsWithCapitals>
```

Para obtener más información acerca de las colecciones de diccionario, vea la sección "reglas avanzadas de colección" más adelante en este tema.

## <a name="collections-and-known-types"></a>Colecciones y tipos conocidos

No necesita agregar tipos de colección a los tipos conocidos al utilizarlos polimórficamente en lugar de otras colecciones o interfaces de colección. Por ejemplo, si declara un miembro de datos de tipo <xref:System.Collections.IEnumerable> y lo utiliza para enviar una instancia de <xref:System.Collections.ArrayList>, no necesita agregar <xref:System.Collections.ArrayList> a los tipos conocidos.

Si se usan colecciones polimórficamente en lugar de tipos de no colección, deben agregarse a tipos conocidos. Por ejemplo, si declara un miembro de datos de tipo `Object` y lo usa para enviar una instancia de <xref:System.Collections.ArrayList>, necesita agregar <xref:System.Collections.ArrayList> a los tipos conocidos.

Esto no le permite serializar polimórficamente cualquier colección equivalente. Por ejemplo, el hecho de agregar <xref:System.Collections.ArrayList> a la lista de tipos conocidos en el ejemplo anterior no le permite asignar la clase `Array of Object` , aunque tenga un contrato de datos equivalente. Este comportamiento no es diferente al de los tipos conocidos normales en la serialización de tipos de no colección, pero es especialmente importante tenerlo claro en el caso de las colecciones, porque es muy frecuente que las colecciones sean equivalentes.

Durante la serialización, solo un tipo puede ser conocido en un ámbito dado para un contrato de datos determinado, y todas las colecciones equivalentes tienen los mismos contratos de datos. Esto significa que, en el ejemplo anterior, no se puede agregar <xref:System.Collections.ArrayList> y `Array of Object` a tipos conocidos en el mismo ámbito. De nuevo, esto equivale al comportamiento de tipos conocidos para los tipos de no colección, pero es especialmente importante entenderlo para las colecciones.

Los tipos conocidos también se pueden requerir para el contenido de colecciones. Por ejemplo, si <xref:System.Collections.ArrayList> realmente contiene instancias de `Type1` y `Type2`, estos dos tipos se deberían agregar a los tipos conocidos.

El ejemplo siguiente muestra un gráfico de objeto correctamente construido utilizando colecciones y tipos conocidos. (El ejemplo está un poco retocado, porque en una aplicación real normalmente no se definirían los miembros de datos siguientes como `Object`y, por consiguiente, no tendría problemas con los tipos conocidos o de polimorfismo.)

[!code-csharp[c_collection_types_in_data_contracts#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#6)]
[!code-vb[c_collection_types_in_data_contracts#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#6)]

Durante la deserialización, si el tipo declarado es un tipo de colección, se crea la instancia del tipo declarado independientemente del tipo que realmente se envió. Si el tipo declarado es una interfaz de colección, el deserializador escoge un tipo a partir del cual se va a crear una instancia independientemente de los tipos conocidos.

También durante la deserialización, si el tipo declarado no es un tipo de colección pero se está enviando un tipo de colección, se seleccionará un tipo de colección coincidente de la lista de tipos conocidos. Es posible agregar los tipos de interfaz de colección a la lista de tipos conocidos durante la deserialización. En este caso, el motor de la deserialización escoge de nuevo un tipo a partir del cual se va a crear una instancia.

## <a name="collections-and-the-netdatacontractserializer-class"></a>Colecciones y la clase NetDataContractSerializer

Cuando se usa la clase <xref:System.Runtime.Serialization.NetDataContractSerializer> , los tipos de colección no personalizados (sin el atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> ) que no son matrices pierden su significado especial.

La clase <xref:System.SerializableAttribute> todavía puede serializar los tipos de colección no personalizados marcados con el atributo <xref:System.Runtime.Serialization.NetDataContractSerializer> de conformidad con el atributo <xref:System.SerializableAttribute> o las reglas de interfaz <xref:System.Runtime.Serialization.ISerializable> .

Los tipos de colección personalizados, las interfaces de colección y las matrices todavía se tratan como colecciones, incluso cuando la clase <xref:System.Runtime.Serialization.NetDataContractSerializer> está en uso.

## <a name="collections-and-schema"></a>Colecciones y esquema

Todas las colecciones equivalentes tienen la misma representación en lenguaje de definición de esquemas XML (XSD). Como consecuencia, normalmente no se obtiene el mismo tipo de colección en el código de cliente generado y en el servidor. Por ejemplo, el servidor puede utilizar un contrato de datos con una <xref:System.Collections.Generic.List%601> genérica de miembro de datos entero, pero en el código de cliente generado el mismo miembro de datos se puede convertir en una matriz de enteros.

Las colecciones de diccionario se marcan con una anotación de esquema específica de WCF que indica que son diccionarios; de lo contrario, no se distinguen de las listas simples que contienen entradas con una clave y un valor. Para una descripción exacta de cómo se representan las colecciones en el esquema del contrato de datos, consulte [Data Contract Schema Reference](data-contract-schema-reference.md).

De forma predeterminada, no se generan tipos para las colecciones no personalizadas en el código importado. Los miembros de datos de tipos de colección de listas se importan como matrices, y los miembros de datos de tipos de colección de diccionarios se importan como diccionario genérico.

Sin embargo, para las colecciones personalizadas, se generan tipos separados, marcados con el atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> . (Un tipo de colección personalizado en el esquema es aquél que no utiliza el espacio de nombres predeterminado, el nombre, el nombre de elemento de repetición o los nombres de elementos de clave y valor). Estos tipos son tipos vacíos que derivan de genéricos <xref:System.Collections.Generic.List%601> para tipos de lista y Diccionario genérico para tipos de diccionario.

Por ejemplo, puede tener los tipos siguientes en el servidor.

[!code-csharp[c_collection_types_in_data_contracts#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#7)]
[!code-vb[c_collection_types_in_data_contracts#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#7)]

Cuando el esquema se exporta y se vuelve a importar, el código de cliente generado es similar al siguiente (para facilitar la lectura, se muestran los campos en lugar de las propiedades).

[!code-csharp[c_collection_types_in_data_contracts#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#8)]
[!code-vb[c_collection_types_in_data_contracts#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#8)]

Puede desear utilizar unos tipos en el código generado que sean diferentes a los predeterminados. Por ejemplo, puede desear utilizar <xref:System.ComponentModel.BindingList%601> genérica en lugar de las matrices normales para sus miembros de datos para que sea más fácil enlazarlos a los componentes de la interfaz de usuario.

Para elegir los tipos de colección a generar, pase una lista de tipos de colección que desee utilizar en la propiedad <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> del objeto <xref:System.Runtime.Serialization.ImportOptions> al importar el esquema. Estos tipos se denominan *tipos de colección de referencia*.

Cuando se hace referencia a tipos genéricos, deben ser genéricos totalmente abiertos o genéricos totalmente cerrados.

> [!NOTE]
> Al usar la herramienta Svcutil.exe, la referencia se puede realizar mediante el uso del modificador de la línea de comandos **/collectionType** (forma corta: **/ct**). Tenga en cuenta que también debe especificar el ensamblado para los tipos de colección a los que se hace referencia mediante el uso del modificador **/reference** (forma corta: **/r**). Si el tipo es genérico, debe ir seguido de una comilla atrás y el número de parámetros genéricos. La comilla ( \` ) no se debe confundir con el carácter de comilla simple ('). Puede especificar varios tipos de colección de referencia mediante el uso del modificador **/collectionType** más de una vez.

Por ejemplo, para que todas las listas se importen como de tipo <xref:System.Collections.Generic.List%601>genérico.

```console
svcutil.exe MyService.wsdl MyServiceSchema.xsd /r:C:\full_path_to_system_dll\System.dll /ct:System.Collections.Generic.List`1
```

Al importar una colección, se escanea esta lista de tipos de colección de referencia y se utiliza la colección más coincidente (si se encuentra una), ya sea como un tipo de miembro de datos (para las colecciones no personalizadas) o como un tipo base del que derivar (para las colecciones personalizadas). Los diccionarios solo se confrontan con los diccionarios, mientras las listas se confrontan con las listas.

Por ejemplo, si agrega la <xref:System.ComponentModel.BindingList%601> genérica y <xref:System.Collections.Hashtable> a la lista de tipos de referencia, el código de cliente generado para el ejemplo anterior es similar al siguiente.

[!code-csharp[c_collection_types_in_data_contracts#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#9)]
[!code-vb[c_collection_types_in_data_contracts#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#9)]

Puede especificar los tipos de interfaz de colección como parte de sus tipos de colección de referencia, pero no puede especificar tipos de colección no válidos (como aquellos sin método `Add` o constructor público).

Se considera que un tipo genérico cerrado es el que más coincide. (Los tipos no genéricos se consideran equivalentes a los genéricos cerrados de `Object`.) Por ejemplo, si los tipos <xref:System.Collections.Generic.List%601> genéricos de <xref:System.DateTime>, <xref:System.ComponentModel.BindingList%601> genérico (abrir genérico), y <xref:System.Collections.ArrayList> son los tipos de colección de referencia, se genera lo siguiente.

[!code-csharp[c_collection_types_in_data_contracts#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#10)]
[!code-vb[c_collection_types_in_data_contracts#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#10)]

Para las colecciones de lista, solo se admiten los casos de la tabla siguiente.

|Tipo de referencia|Interfaz implementada por el tipo de referencia|Ejemplo|Tipo tratado como:|
|---------------------|----------------------------------------------|-------------|----------------------|
|No genérico o genérico cerrado (cualquier número de parámetros)|No genérico|`MyType : IList`<br /><br /> o<br /><br /> `MyType<T> : IList`<br /><br /> donde T= `int`|Genérico cerrado de `Object` (por ejemplo, `IList<object>`)|
|No genérico o genérico cerrado (cualquier número de parámetros que no necesariamente coincide con el tipo de colección)|Genérico cerrado|`MyType : IList<string>`<br /><br /> o<br /><br /> `MyType<T> : IList<string>` donde T=`int`|Genérico cerrado (por ejemplo, `IList<string>`)|
|Genérico cerrado con cualquier número de parámetros|Abrir genérico utilizando cualquiera de los parámetros del tipo|`MyType<T,U,V> : IList<U>`<br /><br /> donde T=`int`, U=`string`, V=`bool`|Genérico cerrado (por ejemplo, `IList<string>`)|
|Genérico abierto con un parámetro|Abrir genérico utilizando el parámetro del tipo|`MyType<T> : IList<T>`, T está abierto|Genérico abierto (por ejemplo, `IList<T>`)|

Si un tipo implementa más de una interfaz de colección de listas, se aplican las restricciones siguientes:

- Si el tipo implementa varias veces <xref:System.Collections.Generic.IEnumerable%601> genérica (o sus interfaces derivadas) para los diferentes tipos, el tipo no se considera un tipo de colección de referencia válido y se ignora. Esto es verdad aun cuando algunas implementaciones no sean válidas o utilicen genéricos abiertos. Por ejemplo, un tipo que implementa <xref:System.Collections.Generic.IEnumerable%601> genérica de `int` y <xref:System.Collections.Generic.IEnumerable%601> genérica de T nunca se utilizaría como una colección de referencia de `int` o cualquier otro tipo, independientemente de si el tipo tiene un método `Add` que acepta `int` o un método `Add` que acepta un parámetro de tipo T, o ambos.

- Si el tipo implementa una interfaz de colección genérica así como <xref:System.Collections.IList>, el tipo nunca se usa como un tipo de colección de referencia a menos que la interfaz de colección genérica sea cerrada genérica de tipo <xref:System.Object>.

Para las colecciones de diccionario, solo se admiten los casos de la tabla siguiente.

|Tipo de referencia|Interfaz implementada por el tipo de referencia|Ejemplo|Tipo tratado como|
|---------------------|----------------------------------------------|-------------|---------------------|
|No genérico o genérico cerrado (cualquier número de parámetros)|<xref:System.Collections.IDictionary>|`MyType : IDictionary`<br /><br /> o<br /><br /> `MyType<T> : IDictionary` donde T=`int`|Genérico cerrado `IDictionary<object,object>`|
|Genérico cerrado (cualquier número de parámetros)|<xref:System.Collections.Generic.IDictionary%602>, cerrado|`MyType<T> : IDictionary<string, bool>` donde T=`int`|Genérico cerrado (por ejemplo, `IDIctionary<string,bool>`)|
|Genérico cerrado (cualquier número de parámetros)|<xref:System.Collections.Generic.IDictionary%602>genérico, o clave o valor está cerrado, el otro está abierto y utiliza uno de los parámetros de tipo|`MyType<T,U,V> : IDictionary<string,V>` donde T=`int`, U=`float`, V=`bool`<br /><br /> o<br /><br /> `MyType<Z> : IDictionary<Z,bool>` donde Z=`string`|Genérico cerrado (por ejemplo, `IDictionary<string,bool>`)|
|Genérico cerrado (cualquier número de parámetros)|<xref:System.Collections.Generic.IDictionary%602>genérico, tanto clave como valor están abiertos y cada uno utiliza uno de los parámetros del tipo|`MyType<T,U,V> : IDictionary<V,U>` donde T=`int`, U=`bool`, V=`string`|Genérico cerrado (por ejemplo, `IDictionary<string,bool>`)|
|Genérico abierto (dos parámetros)|<xref:System.Collections.Generic.IDictionary%602>genérico, abrir, utiliza los dos parámetros genéricos del tipo en el orden que aparecen|`MyType<K,V> : IDictionary<K,V>`, tanto K como V están abiertos|Genérico abierto (por ejemplo, `IDictionary<K,V>`)|

Si el tipo implementa tanto <xref:System.Collections.IDictionary> y <xref:System.Collections.Generic.IDictionary%602>genérica, solo se considera <xref:System.Collections.Generic.IDictionary%602> genérica.

No permite hacer referencia a los tipos genéricos parciales.

No se permiten los duplicados; por ejemplo, no se puede agregar la colección genérica <xref:System.Collections.Generic.List%601> de `Integer` y la colección genérica de `Integer` a <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A>, porque sería imposible determinar cuál de las dos se debe usar cuando se encuentre una lista de enteros en el esquema. Los duplicados se detectan solo si hay un tipo en el esquema que expone el problema de los duplicados. Por ejemplo, si el esquema que se importa no contiene listas de enteros, está permitido tener tanto <xref:System.Collections.Generic.List%601> genérica de `Integer` como la colección genérica de `Integer` en <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A>, pero ninguna tiene efecto.

## <a name="advanced-collection-rules"></a>Reglas avanzadas de colección

### <a name="serializing-collections"></a>Serialización de colecciones

A continuación, se muestra una lista de las reglas de colección para la serialización:

- Se permite combinar los tipos de colección (tener colecciones de colecciones). Las matrices escalonadas se tratan como colecciones de colecciones. No se soportan matrices multidimensionales.

- Las matrices de byte y matrices de <xref:System.Xml.XmlNode> son los tipos de matriz especiales que se tratan como primitivas, no colecciones. Al serializar una matriz de bytes se obtiene un elemento XML único que contiene un bloque de datos con codificación Base64, en lugar de un elemento aparte para cada byte. Para obtener más información sobre cómo se trata una matriz de <xref:System.Xml.XmlNode> , vea [tipos XML y ADO.net en los contratos de datos](xml-and-ado-net-types-in-data-contracts.md). Evidentemente, estos tipos especiales pueden participar en colecciones: una matriz de matriz de byte resulta en múltiples elementos XML, y cada uno de ellos contiene un bloque de datos codificados por Base64.

- Si el atributo <xref:System.Runtime.Serialization.DataContractAttribute> se aplica a un tipo de colección, el tipo se trata como un tipo de contrato de datos normal, no como una colección.

- Si un tipo de colección implementa la interfaz <xref:System.Xml.Serialization.IXmlSerializable> , se aplican las siguientes reglas dado un tipo `myType:IList<string>, IXmlSerializable`:

  - Si el tipo declarado es `IList<string>`, el tipo se serializa como una lista.

  - Si el tipo declarado es `myType`, se serializa como `IXmlSerializable`.

  - Si el tipo declarado es `IXmlSerializable`, se serializa como `IXmlSerializable`, pero solo si se agrega `myType` a la lista de tipos conocidos.

- Las colecciones se serializan y deserializan con los métodos que se muestran en la tabla siguiente.

|El tipo de colección implementa|Los métodos llamados durante la serialización|Métodos llamados durante la deserialización|
|--------------------------------|-----------------------------------------|-------------------------------------------|
|Generic <ph id="ph1">&lt;xref:System.Collections.Generic.IDictionary%602&gt;</ph>|`get_Keys`, `get_Values`|Agregar genérico|
|<xref:System.Collections.IDictionary>|`get_Keys`, `get_Values`|`Add`|
|Generic <ph id="ph1">&lt;xref:System.Collections.Generic.IList%601&gt;</ph>|Indizador <xref:System.Collections.Generic.IList%601> genérico|Agregar genérico|
|Generic <ph id="ph1">&lt;xref:System.Collections.Generic.ICollection%601&gt;</ph>|Enumerador|Agregar genérico|
|<xref:System.Collections.IList>|<xref:System.Collections.IList> Indizador|`Add`|
|Generic <ph id="ph1">&lt;xref:System.Collections.Generic.IEnumerable%601&gt;</ph>|`GetEnumerator`|Un método no estático llamado `Add` que toma un parámetro del tipo adecuado (el tipo del parámetro genérico o uno de sus tipos base). Este tipo de método debe existir para que el serializador pueda tratar un tipo de colección como una colección durante serialización y deserialización.|
|<xref:System.Collections.IEnumerable> (y por consiguiente <xref:System.Collections.ICollection>, que deriva de él)|`GetEnumerator`|Un método no estático llamado `Add` que toma un parámetro de tipo `Object`. Este tipo de método debe existir para que el serializador pueda tratar un tipo de colección como una colección durante serialización y deserialización.|

En la tabla anterior se muestran las interfaces de colección en orden descendente de prioridad. Por ejemplo, esto significa que si un tipo implementa tanto <xref:System.Collections.IList> como <xref:System.Collections.Generic.IEnumerable%601>genérica, la colección se serializa y deserializa según las reglas <xref:System.Collections.IList> :

- En la deserialización, todas las colecciones se deserializan creando primero una instancia del tipo llamando al constructor sin parámetros, que debe estar presente para que el serializador trate un tipo de colección como una colección durante la serialización y la deserialización.

- Si se implementa la misma interfaz de colección genérica más de una vez (por ejemplo, si un tipo implementa tanto <xref:System.Collections.Generic.ICollection%601> genérica de `Integer` como <xref:System.Collections.Generic.ICollection%601> genérica de <xref:System.String>) y no se encuentra ninguna interfaz de la prioridad más alta, la colección no se trata como una colección válida.

- Los tipos de colección pueden tener el atributo <xref:System.SerializableAttribute> aplicado a ellos e implementar la interfaz <xref:System.Runtime.Serialization.ISerializable> . Se ignoran ambos. Sin embargo, si el tipo no cumple totalmente los requisitos del tipo de colección (por ejemplo, no se encuentra el método `Add` ), no se considera un tipo de colección y, por consiguiente, se usan el atributo <xref:System.SerializableAttribute> y la interfaz <xref:System.Runtime.Serialization.ISerializable> para determinar si el tipo se puede serializar.

- Al aplicar el atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> a una colección para personalizarla, se quita el mecanismo de reserva anterior de <xref:System.SerializableAttribute> . En su lugar, si una colección personalizada no cumple los requisitos de tipo de colección, se produce una excepción <xref:System.Runtime.Serialization.InvalidDataContractException> . La cadena de excepción contiene a menudo información que explica por qué un tipo determinado no se considera una colección válida (ningún `Add` método, ningún constructor sin parámetros, etc.), por lo que a menudo resulta útil aplicar el <xref:System.Runtime.Serialization.CollectionDataContractAttribute> atributo con fines de depuración.

### <a name="collection-naming"></a>Denominación de colección

A continuación, se muestra una lista de las reglas para denominar una colección:

- El espacio de nombres predeterminado para todos los contratos de datos de colección de diccionarios, así como para los contratos de datos de colección de listas que contienen tipos primitivos, es `http://schemas.microsoft.com/2003/10/Serialization/Arrays` a menos que se invalide con el espacio de nombres. Los tipos que se asignan a tipos XSD integrados, así como `char`, `Timespan`y los tipos `Guid` , se consideran primitivos para este propósito.

- El espacio de nombres predeterminado para tipos de colección que contienen tipos no primitivos, a menos que se invalide mediante el uso de Namespace, es el mismo que el espacio de nombres de contrato de datos del tipo contenido en la colección.

- El nombre predeterminado para los contratos de datos de colección de listas, a menos que se invalide utilizando Nombre, es la cadena "ArrayOf" combinada con el nombre de contrato de datos del tipo contenido en la colección. Por ejemplo, el nombre de contrato de datos para una lista genérica de enteros es "ArrayOfint." Tenga presente que el nombre de contrato de datos de `Object` es "anyType", de modo que el nombre de contrato de datos de listas no genéricas como <xref:System.Collections.ArrayList> es "ArrayOfanyType."

El nombre predeterminado para los contratos de datos de colección de diccionarios, a menos que se invalide utilizando `Name`, es la cadena "ArrayOfKeyValueOf" combinada con el nombre de contrato de datos del tipo clave seguido por el nombre de contrato de datos del tipo de valor. Por ejemplo, el nombre de contrato de datos para un diccionario genérico de cadena y entero es "ArrayOfKeyValueOfstringint." Adicionalmente, si los tipos de clave o valor no son tipos primitivos, un hash de espacio de nombres de los espacios de nombres de contrato de datos de los tipos de clave y valor se agrega al nombre. Para obtener más información sobre los hash de espacio de nombres, vea [nombres de contratos de datos](data-contract-names.md).

Cada contrato de datos de colección de diccionarios tiene un contrato de datos complementario que representa una entrada en el diccionario. Su nombre es igual que para el contrato de datos del diccionario, salvo el prefijo "ArrayOf", y su espacio de nombres es igual que para el contrato de datos del diccionario. Por ejemplo, para el contrato de datos de diccionario de "ArrayOfKeyValueOfstringint", el contrato de datos de "KeyValueofstringint" representa una entrada en el diccionario. Puede personalizar el nombre de este contrato de datos utilizando la propiedad `ItemName` , como se describe en la sección siguiente.

Las reglas de denominación de tipo genérico, como se describen en [Data Contract Names](data-contract-names.md), se aplican totalmente a los tipos de colección; es decir, puede usar llaves dentro del nombre para indicar los parámetros de tipo genérico. Sin embargo, los números entre llaves hacen referencia a parámetros genéricos y no a tipos contenidos dentro de la colección.

## <a name="collection-customization"></a>Personalización de colección

Los usos siguientes del atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> están prohibidos y producen una excepción <xref:System.Runtime.Serialization.InvalidDataContractException> :

- Aplicar el atributo <xref:System.Runtime.Serialization.DataContractAttribute> a un tipo al que se ha aplicado el atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> o a uno de sus tipos derivados.

- Aplicar el atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> a un tipo que implementa la interfaz <xref:System.Xml.Serialization.IXmlSerializable> .

- Aplicar el atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> a un tipo de no colección.

- Intentando establecer <xref:System.Runtime.Serialization.CollectionDataContractAttribute.KeyName%2A> o <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ValueName%2A> en un atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> aplicado a un tipo de no diccionario.

### <a name="polymorphism-rules"></a>Reglas del polimorfismo

Como se ha mencionado previamente, la personalización de colecciones mediante el atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> puede interferir con la intercambiabilidad de las colecciones. Dos tipos de colección personalizados solo se pueden considerar equivalentes si su nombre, espacio de nombres, nombre de elemento, así como nombres de clave y valor (si son colecciones de diccionarios) coinciden.

Debido a las personalizaciones, es posible utilizar inadvertidamente un contrato de datos de colección donde se espera otro. Éste debería evitarse. Vea los tipos siguientes.

[!code-csharp[c_collection_types_in_data_contracts#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#11)]
[!code-vb[c_collection_types_in_data_contracts#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#11)]

En este caso, una instancia de `Marks1` se puede asignar a `testMarks`. Sin embargo, no se debería utilizar `Marks2` porque su contrato de datos no se considera equivalente al contrato de datos `IList<int>` . El nombre del contrato de datos es "Marks2" y no "ArrayOfint", y el nombre del elemento repetido es " \<mark> " y no " \<int> ".

Las reglas de la tabla siguiente se aplican a la asignación polimórfica de colecciones.

|Tipo declarado|Asignar una colección no personalizada|Asignar una colección personalizada|
|-------------------|--------------------------------------------|---------------------------------------|
|Object|El nombre del contrato está serializado.|El nombre del contrato está serializado.<br /><br /> Se utiliza la personalización.|
|Interfaz de colección|El nombre del contrato no está serializado.|El nombre del contrato no está serializado.<br /><br /> No se utiliza la personalización.\*|
|Colección no personalizada|El nombre del contrato no está serializado.|El nombre del contrato está serializado.<br /><br /> Se utiliza la personalización.**|
|Colección personalizada|El nombre del contrato está serializado. No se utiliza la personalización.\*\*|El nombre del contrato está serializado.<br /><br /> Se utiliza la personalización del tipo asignado.\*\*|

\*Con la <xref:System.Runtime.Serialization.NetDataContractSerializer> clase, en este caso se utiliza la personalización. La clase <xref:System.Runtime.Serialization.NetDataContractSerializer> también serializa el nombre de tipo real en este caso, por lo que la deserialización funciona como se espera.

\*\*Estos casos generan instancias no válidas para el esquema y, por tanto, deben evitarse.

En los casos donde se serializa el nombre del contrato, el tipo de colección asignado debería estar en la lista de tipos conocidos. Lo contrario también es cierto: en los casos en los que no se serializa el nombre, no es necesario agregar el tipo a la lista de tipos conocidos.

Una matriz de un tipo derivado se puede asignar a una matriz de un tipo base. En este caso, el nombre del contrato para el tipo derivado se serializa para cada elemento repetido. Por ejemplo, si un tipo `Book` deriva del tipo `LibraryItem`, puede asignar una matriz de `Book` a una matriz de `LibraryItem`. Esto no se aplica a otros tipos de colección. Por ejemplo, puede asignar `Generic List of Book` a `Generic List of LibraryItem`. Sin embargo, puede asignar `Generic List of LibraryItem` que contiene las instancias `Book` . Tanto en el caso de matriz como de no matriz, `Book` debería estar en la lista de tipos conocidos.

## <a name="collections-and-object-reference-preservation"></a>Preservación de colecciones y de la referencia de objetos

Cuando un serializador funciona en un modo donde preserva las referencias de objetos, la preservación de la referencia de objetos también se aplica a las colecciones. Específicamente, la identidad de objeto se preserva tanto para colecciones completas como para elementos individuales contenidos en colecciones. Para los diccionarios, la identidad de objeto se preserva tanto para los objetos de par clave-valor como para los objetos individuales de clave y valor.

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
