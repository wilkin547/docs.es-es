---
title: Serialización tolerante a versiones
description: Aprenda sobre la serialización tolerante a versiones, un conjunto de características que facilita la modificación de tipos serializables.
ms.date: 08/08/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- version tolerant serialization
- serialization, custom serialization
- serialization, version tolerant
- serialization, controlling
- versions and serialization
- BinaryFormatter class, samples
- serialization, attributes
ms.assetid: bea0ffe3-2708-4a16-ac7d-e586ed6b8e8d
ms.openlocfilehash: e7c4d6ca4c72390c3e0803502aa9c1a675e02345
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282422"
---
# <a name="version-tolerant-serialization"></a>Serialización tolerante a versiones

En las versiones anteriores de .NET Framework, la creación de tipos serializables que serían reutilizables a partir de una versión de una aplicación a lo siguiente, ha resultado problemática. Si un tipo se modificara agregando los campos adicionales, se producirían los problemas siguientes:

- Las versiones anteriores de una aplicación produciría excepciones en caso de solicitar la deserialización de las nuevas versiones del tipo anterior.
- Las versiones más recientes de una aplicación producirían las excepciones al deserializar versiones anteriores de un tipo con datos que faltan.

La serialización tolerante a versiones (VTS) es un conjunto de características que facilita, con el tiempo, modificar los tipos serializables. Específicamente, las características VTS están habilitadas para las clases a las que se ha aplicado el atributo <xref:System.SerializableAttribute>, incluidos los tipos genéricos. VTS posibilita el agregar los nuevos campos a esas clases sin interrumpir la compatibilidad con otras versiones del tipo. Para obtener una aplicación de ejemplo en funcionamiento, vea [Ejemplo de tecnología de serialización tolerante a versiones](basic-serialization-technology-sample.md).

Las características VTS están habilitadas al utilizar <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. Además, todas las características, excepto la tolerancia de datos extraños, están habilitadas también al utilizar <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>. Para más información sobre el uso de estas clases para la serialización, vea [Serialización binaria](binary-serialization.md).

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

## <a name="feature-list"></a>Lista de características

En la lista de características se incluyen las siguientes:

- Tolerancia de datos extraños o inesperados. Esto permite a las versiones más recientes del tipo enviar los datos a las versiones anteriores.
- Tolerancia de datos opcionales que faltan. Esto permite a las versiones anteriores enviar los datos a las versiones más recientes.
- Devoluciones de llamada de la serialización. Esto habilita el valor predeterminado inteligente en casos donde faltan datos.

Hay además, una característica para declarar cuando se ha agregado un nuevo campo opcional. Ésta es la propiedad <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A> del atributo <xref:System.Runtime.Serialization.OptionalFieldAttribute>.

Estas opciones se tratan con más detalle en las secciones siguientes.

### <a name="tolerance-of-extraneous-or-unexpected-data"></a>Tolerancia de datos extraños o inesperados

En el pasado, durante la deserialización, cualquier dato extraño o inesperado produjeron excepciones. Con VTS, en la misma situación, cualquier dato extraño o inesperado se omite en lugar de producir excepciones. Esto habilita aplicaciones que utilizan versiones más recientes de un tipo (es decir, una versión que incluye más campos) para enviar información a las aplicaciones que esperan versiones anteriores del mismo tipo.

En el ejemplo siguiente, los datos adicionales contenidos en `CountryField` de la versión 2.0 de la clase `Address` se omiten cuando una aplicación anterior deserializa la versión más reciente.

```csharp  
// Version 1 of the Address class.  
[Serializable]  
public class Address  
{  
    public string Street;  
    public string City;  
}  
// Version 2.0 of the Address class.  
[Serializable]  
public class Address  
{  
    public string Street;  
    public string City;  
    // The older application ignores this data.  
    public string CountryField;  
}  
```  
  
```vb  
' Version 1 of the Address class.  
<Serializable> _  
Public Class Address  
    Public Street As String  
    Public City As String  
End Class  
  
' Version 2.0 of the Address class.  
<Serializable> _  
Public Class Address  
    Public Street As String  
    Public City As String  
    ' The older application ignores this data.  
    Public CountryField As String  
End Class  
```  

### <a name="tolerance-of-missing-data"></a>Tolerancia de datos que faltan

Los campos se pueden marcar como opcionales aplicando el atributo <xref:System.Runtime.Serialization.OptionalFieldAttribute> a ellos. Durante la deserialización, si faltan datos opcionales, el motor de la serialización omite la ausencia y no inicia una excepción. Así, las aplicaciones que esperan versiones anteriores de un tipo pueden enviar los datos a las aplicaciones que esperan versiones más recientes del mismo tipo.

El ejemplo siguiente muestra la versión 2.0 de la clase `Address` con el campo `CountryField` marcado como opcional. Si una aplicación más anterior envía la versión 1 a una aplicación más reciente que espera la versión 2.0, se omite la ausencia de los datos.

```csharp
[Serializable]
public class Address
{
    public string Street;
    public string City;

    [OptionalField]
    public string CountryField;
}
```

```vb
<Serializable> _
Public Class Address
    Public Street As String
    Public City As String

    <OptionalField> _
    Public CountryField As String
End Class
```
  
### <a name="serialization-callbacks"></a>Devoluciones de llamada de la serialización

Las devoluciones de llamada de la serialización son un mecanismo que proporciona los enlaces en el proceso de serialización/deserialización en cuatro puntos.

|Atributo|Cuando se llama al método asociado.|Uso típico|
|---------------|------------------------------------------|-----------------|
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|Antes de la deserialización.\*|Inicialice los valores predeterminados para los campos opcionales.|
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|Después de la deserialización.|Corrija valores de campo opcionales basados en el contenido de otros campos.|
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|Antes de la serialización.|Prepare para la serialización. Por ejemplo, cree las estructuras de datos opcionales.|
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|Después de la serialización.|Registre los eventos de serialización.|

 \* Esta devolución de llamada se invoca antes del constructor de deserialización, si hay alguno.

#### <a name="using-callbacks"></a>Empleo de devoluciones de llamada

Para utilizar las devoluciones de llamada, aplique el atributo adecuado a un método que acepta un parámetro <xref:System.Runtime.Serialization.StreamingContext>. Solo se puede marcar un método por clase con cada uno de estos atributos. Por ejemplo:

```csharp
[OnDeserializing]
private void SetCountryRegionDefault(StreamingContext sc)
{
    CountryField = "Japan";
}
```

```vb
<OnDeserializing>
Private Sub SetCountryRegionDefault(sc As StreamingContext)
    CountryField = "Japan"
End Sub
```

El uso previsto de estos métodos es para las versiones. Durante la deserialización, un campo opcional no se puede inicializar correctamente si faltan los datos para el campo. Esto se puede corregir si se crea el método que asigna el valor correcto y luego se aplica el atributo **OnDeserializingAttribute** u **OnDeserializedAttribute** al método.

El ejemplo siguiente muestra el método en el contexto de un tipo. Si una versión anterior de una aplicación envía una instancia de la clase `Address` a una versión posterior de la aplicación, faltarán los datos de campo `CountryField`. Pero después de la deserialización, el campo se establecerá en el valor predeterminado "Japan".

```csharp
[Serializable]
public class Address
{
    public string Street;
    public string City;
    [OptionalField]
    public string CountryField;

    [OnDeserializing]
    private void SetCountryRegionDefault(StreamingContext sc)
    {
        CountryField = "Japan";
    }
}
```

```vb
<Serializable> _
Public Class Address
    Public Street As String
    Public City As String
    <OptionalField> _
    Public CountryField As String

    <OnDeserializing> _
    Private Sub SetCountryRegionDefault(sc As StreamingContext)
        CountryField = "Japan"
    End Sub
End Class
```

## <a name="the-versionadded-property"></a>Propiedad VersionAdded

**OptionalFieldAttribute** tiene la propiedad **VersionAdded**. La propiedad indica qué versión de un tipo de un campo determinado se ha agregado. Se debería incrementar en uno exactamente (comenzando en 2) cada vez que se modifica el tipo, como se muestra en el ejemplo siguiente:

```csharp
// Version 1.0
[Serializable]
public class Person
{
    public string FullName;
}

// Version 2.0
[Serializable]
public class Person
{
    public string FullName;

    [OptionalField(VersionAdded = 2)]
    public string NickName;
    [OptionalField(VersionAdded = 2)]
    public DateTime BirthDate;
}

// Version 3.0
[Serializable]
public class Person
{
    public string FullName;

    [OptionalField(VersionAdded=2)]
    public string NickName;
    [OptionalField(VersionAdded=2)]
    public DateTime BirthDate;

    [OptionalField(VersionAdded=3)]
    public int Weight;
}
```

```vb
' Version 1.0
<Serializable> _
Public Class Person
    Public FullName
End Class

' Version 2.0
<Serializable> _
Public Class Person
    Public FullName As String

    <OptionalField(VersionAdded := 2)> _
    Public NickName As String
    <OptionalField(VersionAdded := 2)> _
    Public BirthDate As DateTime
End Class

' Version 3.0
<Serializable> _
Public Class Person
    Public FullName As String

    <OptionalField(VersionAdded := 2)> _
    Public NickName As String
    <OptionalField(VersionAdded := 2)> _
    Public BirthDate As DateTime

    <OptionalField(VersionAdded := 3)> _
    Public Weight As Integer
End Class
```

## <a name="serializationbinder"></a>SerializationBinder

Algunos usuarios pueden necesitar controlar qué clase serializar y deserializar porque se necesita una versión diferente de la clase en el servidor y el cliente. <xref:System.Runtime.Serialization.SerializationBinder> es una clase abstracta usada para controlar los tipos reales empleados durante la serialización y la deserialización. Para usar esta clase, obtenga una clase de <xref:System.Runtime.Serialization.SerializationBinder> y omita los métodos <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> y <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A>. Para obtener más información, vea [Control de la serialización y la deserialización con SerializationBinder](../../framework/wcf/feature-details/controlling-serialization-and-deserialization-with-serializationbinder.md).

## <a name="best-practices"></a>Procedimientos recomendados

Para asegurar el comportamiento apropiado de la versión, siga estas reglas al modificar un tipo de la versión para la versión:

- Nunca quite un campo serializado.
- Nunca aplique el atributo <xref:System.NonSerializedAttribute> a un campo si el atributo no se aplicó al campo en la versión anterior.
- Nunca cambie el nombre o el tipo de un campo serializado.
- Al agregar un nuevo campo serializado, aplique el atributo **OptionalFieldAttribute**.
- Al quitar un atributo **NonSerializedAttribute** de un campo (que no era serializable en una versión anterior), aplique el atributo **OptionalFieldAttribute**.
- Para todos los campos opcionales, establezca valores predeterminados significativos mediante las devoluciones de llamada de serialización, a menos que se acepten 0 o **null** como valores predeterminados.

Para asegurarse de que un tipo será compatible con motores de serialización futuros, siga estas instrucciones:

- Establezca siempre correctamente la propiedad **VersionAdded** en el atributo **OptionalFieldAttribute**.
- Evite la versión bifurcada.

## <a name="see-also"></a>Vea también

- <xref:System.SerializableAttribute>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
- <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A>
- <xref:System.Runtime.Serialization.OptionalFieldAttribute>
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>
- <xref:System.Runtime.Serialization.OnSerializingAttribute>
- <xref:System.Runtime.Serialization.OnSerializedAttribute>
- <xref:System.Runtime.Serialization.StreamingContext>
- <xref:System.NonSerializedAttribute>
- [Serialización binaria](binary-serialization.md)
