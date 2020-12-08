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
ms.openlocfilehash: 26612c5b0591efa61fcd476733aee2b219d67c62
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96438168"
---
# <a name="version-tolerant-serialization"></a><span data-ttu-id="26cf2-103">Serialización tolerante a versiones</span><span class="sxs-lookup"><span data-stu-id="26cf2-103">Version tolerant serialization</span></span>

<span data-ttu-id="26cf2-104">En las versiones anteriores de .NET Framework, la creación de tipos serializables que serían reutilizables a partir de una versión de una aplicación a lo siguiente, ha resultado problemática.</span><span class="sxs-lookup"><span data-stu-id="26cf2-104">In the earliest versions of .NET Framework, creating serializable types that would be reusable from one version of an application to the next was problematic.</span></span> <span data-ttu-id="26cf2-105">Si un tipo se modificara agregando los campos adicionales, se producirían los problemas siguientes:</span><span class="sxs-lookup"><span data-stu-id="26cf2-105">If a type was modified by adding extra fields, the following problems would occur:</span></span>

- <span data-ttu-id="26cf2-106">Las versiones anteriores de una aplicación produciría excepciones en caso de solicitar la deserialización de las nuevas versiones del tipo anterior.</span><span class="sxs-lookup"><span data-stu-id="26cf2-106">Older versions of an application would throw exceptions when asked to deserialize new versions of the old type.</span></span>
- <span data-ttu-id="26cf2-107">Las versiones más recientes de una aplicación producirían las excepciones al deserializar versiones anteriores de un tipo con datos que faltan.</span><span class="sxs-lookup"><span data-stu-id="26cf2-107">Newer versions of an application would throw exceptions when deserializing older versions of a type with missing data.</span></span>

<span data-ttu-id="26cf2-108">La serialización tolerante a versiones (VTS) es un conjunto de características que facilita, con el tiempo, modificar los tipos serializables.</span><span class="sxs-lookup"><span data-stu-id="26cf2-108">Version Tolerant Serialization (VTS) is a set of features that makes it easier, over time, to modify serializable types.</span></span> <span data-ttu-id="26cf2-109">Específicamente, las características VTS están habilitadas para las clases a las que se ha aplicado el atributo <xref:System.SerializableAttribute>, incluidos los tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="26cf2-109">Specifically, the VTS features are enabled for classes to which the <xref:System.SerializableAttribute> attribute has been applied, including generic types.</span></span> <span data-ttu-id="26cf2-110">VTS posibilita el agregar los nuevos campos a esas clases sin interrumpir la compatibilidad con otras versiones del tipo.</span><span class="sxs-lookup"><span data-stu-id="26cf2-110">VTS makes it possible to add new fields to those classes without breaking compatibility with other versions of the type.</span></span>

<span data-ttu-id="26cf2-111">Las características VTS están habilitadas al utilizar <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="26cf2-111">The VTS features are enabled when using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span> <span data-ttu-id="26cf2-112">Además, todas las características, excepto la tolerancia de datos extraños, están habilitadas también al utilizar <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span><span class="sxs-lookup"><span data-stu-id="26cf2-112">Additionally, all features except extraneous data tolerance are also enabled when using the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span></span> <span data-ttu-id="26cf2-113">Para más información sobre el uso de estas clases para la serialización, vea [Serialización binaria](binary-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="26cf2-113">For more information about using these classes for serialization, see [Binary Serialization](binary-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

## <a name="feature-list"></a><span data-ttu-id="26cf2-114">Lista de características</span><span class="sxs-lookup"><span data-stu-id="26cf2-114">Feature list</span></span>

<span data-ttu-id="26cf2-115">En la lista de características se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="26cf2-115">The set of features includes the following:</span></span>

- <span data-ttu-id="26cf2-116">Tolerancia de datos extraños o inesperados.</span><span class="sxs-lookup"><span data-stu-id="26cf2-116">Tolerance of extraneous or unexpected data.</span></span> <span data-ttu-id="26cf2-117">Esto permite a las versiones más recientes del tipo enviar los datos a las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="26cf2-117">This enables newer versions of the type to send data to older versions.</span></span>
- <span data-ttu-id="26cf2-118">Tolerancia de datos opcionales que faltan.</span><span class="sxs-lookup"><span data-stu-id="26cf2-118">Tolerance of missing optional data.</span></span> <span data-ttu-id="26cf2-119">Esto permite a las versiones anteriores enviar los datos a las versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="26cf2-119">This enables older versions to send data to newer versions.</span></span>
- <span data-ttu-id="26cf2-120">Devoluciones de llamada de la serialización.</span><span class="sxs-lookup"><span data-stu-id="26cf2-120">Serialization callbacks.</span></span> <span data-ttu-id="26cf2-121">Esto habilita el valor predeterminado inteligente en casos donde faltan datos.</span><span class="sxs-lookup"><span data-stu-id="26cf2-121">This enables intelligent default value setting in cases where data is missing.</span></span>

<span data-ttu-id="26cf2-122">Hay además, una característica para declarar cuando se ha agregado un nuevo campo opcional.</span><span class="sxs-lookup"><span data-stu-id="26cf2-122">In addition, there is a feature for declaring when a new optional field has been added.</span></span> <span data-ttu-id="26cf2-123">Ésta es la propiedad <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A> del atributo <xref:System.Runtime.Serialization.OptionalFieldAttribute>.</span><span class="sxs-lookup"><span data-stu-id="26cf2-123">This is the <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A> property of the <xref:System.Runtime.Serialization.OptionalFieldAttribute> attribute.</span></span>

<span data-ttu-id="26cf2-124">Estas opciones se tratan con más detalle en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="26cf2-124">These features are discussed in greater detail in the following sections.</span></span>

### <a name="tolerance-of-extraneous-or-unexpected-data"></a><span data-ttu-id="26cf2-125">Tolerancia de datos extraños o inesperados</span><span class="sxs-lookup"><span data-stu-id="26cf2-125">Tolerance of extraneous or unexpected data</span></span>

<span data-ttu-id="26cf2-126">En el pasado, durante la deserialización, cualquier dato extraño o inesperado produjeron excepciones.</span><span class="sxs-lookup"><span data-stu-id="26cf2-126">In the past, during deserialization, any extraneous or unexpected data caused exceptions to be thrown.</span></span> <span data-ttu-id="26cf2-127">Con VTS, en la misma situación, cualquier dato extraño o inesperado se omite en lugar de producir excepciones.</span><span class="sxs-lookup"><span data-stu-id="26cf2-127">With VTS, in the same situation, any extraneous or unexpected data is ignored instead of causing exceptions to be thrown.</span></span> <span data-ttu-id="26cf2-128">Esto habilita aplicaciones que utilizan versiones más recientes de un tipo (es decir, una versión que incluye más campos) para enviar información a las aplicaciones que esperan versiones anteriores del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="26cf2-128">This enables applications that use newer versions of a type (that is, a version that includes more fields) to send information to applications that expect older versions of the same type.</span></span>

<span data-ttu-id="26cf2-129">En el ejemplo siguiente, los datos adicionales contenidos en `CountryField` de la versión 2.0 de la clase `Address` se omiten cuando una aplicación anterior deserializa la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="26cf2-129">In the following example, the extra data contained in the `CountryField` of version 2.0 of the `Address` class is ignored when an older application deserializes the newer version.</span></span>

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

### <a name="tolerance-of-missing-data"></a><span data-ttu-id="26cf2-130">Tolerancia de datos que faltan</span><span class="sxs-lookup"><span data-stu-id="26cf2-130">Tolerance of missing data</span></span>

<span data-ttu-id="26cf2-131">Los campos se pueden marcar como opcionales aplicando el atributo <xref:System.Runtime.Serialization.OptionalFieldAttribute> a ellos.</span><span class="sxs-lookup"><span data-stu-id="26cf2-131">Fields can be marked as optional by applying the <xref:System.Runtime.Serialization.OptionalFieldAttribute> attribute to them.</span></span> <span data-ttu-id="26cf2-132">Durante la deserialización, si faltan datos opcionales, el motor de la serialización omite la ausencia y no inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="26cf2-132">During deserialization, if the optional data is missing, the serialization engine ignores the absence and does not throw an exception.</span></span> <span data-ttu-id="26cf2-133">Así, las aplicaciones que esperan versiones anteriores de un tipo pueden enviar los datos a las aplicaciones que esperan versiones más recientes del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="26cf2-133">Thus, applications that expect older versions of a type can send data to applications that expect newer versions of the same type.</span></span>

<span data-ttu-id="26cf2-134">El ejemplo siguiente muestra la versión 2.0 de la clase `Address` con el campo `CountryField` marcado como opcional.</span><span class="sxs-lookup"><span data-stu-id="26cf2-134">The following example shows version 2.0 of the `Address` class with the `CountryField` field marked as optional.</span></span> <span data-ttu-id="26cf2-135">Si una aplicación más anterior envía la versión 1 a una aplicación más reciente que espera la versión 2.0, se omite la ausencia de los datos.</span><span class="sxs-lookup"><span data-stu-id="26cf2-135">If an older application sends version 1 to a newer application that expects version 2.0, the absence of the data is ignored.</span></span>

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
  
### <a name="serialization-callbacks"></a><span data-ttu-id="26cf2-136">Devoluciones de llamada de la serialización</span><span class="sxs-lookup"><span data-stu-id="26cf2-136">Serialization callbacks</span></span>

<span data-ttu-id="26cf2-137">Las devoluciones de llamada de la serialización son un mecanismo que proporciona los enlaces en el proceso de serialización/deserialización en cuatro puntos.</span><span class="sxs-lookup"><span data-stu-id="26cf2-137">Serialization callbacks are a mechanism that provides hooks into the serialization/deserialization process at four points.</span></span>

|<span data-ttu-id="26cf2-138">Atributo</span><span class="sxs-lookup"><span data-stu-id="26cf2-138">Attribute</span></span>|<span data-ttu-id="26cf2-139">Cuando se llama al método asociado.</span><span class="sxs-lookup"><span data-stu-id="26cf2-139">When the Associated Method is Called</span></span>|<span data-ttu-id="26cf2-140">Uso típico</span><span class="sxs-lookup"><span data-stu-id="26cf2-140">Typical Use</span></span>|
|---------------|------------------------------------------|-----------------|
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|<span data-ttu-id="26cf2-141">Antes de la deserialización.\*</span><span class="sxs-lookup"><span data-stu-id="26cf2-141">Before deserialization.\*</span></span>|<span data-ttu-id="26cf2-142">Inicialice los valores predeterminados para los campos opcionales.</span><span class="sxs-lookup"><span data-stu-id="26cf2-142">Initialize default values for optional fields.</span></span>|
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|<span data-ttu-id="26cf2-143">Después de la deserialización.</span><span class="sxs-lookup"><span data-stu-id="26cf2-143">After deserialization.</span></span>|<span data-ttu-id="26cf2-144">Corrija valores de campo opcionales basados en el contenido de otros campos.</span><span class="sxs-lookup"><span data-stu-id="26cf2-144">Fix optional field values based on contents of other fields.</span></span>|
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|<span data-ttu-id="26cf2-145">Antes de la serialización.</span><span class="sxs-lookup"><span data-stu-id="26cf2-145">Before serialization.</span></span>|<span data-ttu-id="26cf2-146">Prepare para la serialización.</span><span class="sxs-lookup"><span data-stu-id="26cf2-146">Prepare for serialization.</span></span> <span data-ttu-id="26cf2-147">Por ejemplo, cree las estructuras de datos opcionales.</span><span class="sxs-lookup"><span data-stu-id="26cf2-147">For example, create optional data structures.</span></span>|
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|<span data-ttu-id="26cf2-148">Después de la serialización.</span><span class="sxs-lookup"><span data-stu-id="26cf2-148">After serialization.</span></span>|<span data-ttu-id="26cf2-149">Registre los eventos de serialización.</span><span class="sxs-lookup"><span data-stu-id="26cf2-149">Log serialization events.</span></span>|

 <span data-ttu-id="26cf2-150">\* Esta devolución de llamada se invoca antes del constructor de deserialización, si hay alguno.</span><span class="sxs-lookup"><span data-stu-id="26cf2-150">\* This callback is invoked before the deserialization constructor, if one is present.</span></span>

#### <a name="using-callbacks"></a><span data-ttu-id="26cf2-151">Empleo de devoluciones de llamada</span><span class="sxs-lookup"><span data-stu-id="26cf2-151">Using callbacks</span></span>

<span data-ttu-id="26cf2-152">Para utilizar las devoluciones de llamada, aplique el atributo adecuado a un método que acepta un parámetro <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="26cf2-152">To use callbacks, apply the appropriate attribute to a method that accepts a <xref:System.Runtime.Serialization.StreamingContext> parameter.</span></span> <span data-ttu-id="26cf2-153">Solo se puede marcar un método por clase con cada uno de estos atributos.</span><span class="sxs-lookup"><span data-stu-id="26cf2-153">Only one method per class can be marked with each of these attributes.</span></span> <span data-ttu-id="26cf2-154">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="26cf2-154">For example:</span></span>

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

<span data-ttu-id="26cf2-155">El uso previsto de estos métodos es para las versiones.</span><span class="sxs-lookup"><span data-stu-id="26cf2-155">The intended use of these methods is for versioning.</span></span> <span data-ttu-id="26cf2-156">Durante la deserialización, un campo opcional no se puede inicializar correctamente si faltan los datos para el campo.</span><span class="sxs-lookup"><span data-stu-id="26cf2-156">During deserialization, an optional field may not be correctly initialized if the data for the field is missing.</span></span> <span data-ttu-id="26cf2-157">Esto se puede corregir si se crea el método que asigna el valor correcto y luego se aplica el atributo **OnDeserializingAttribute** u **OnDeserializedAttribute** al método.</span><span class="sxs-lookup"><span data-stu-id="26cf2-157">This can be corrected by creating the method that assigns the correct value, then applying either the **OnDeserializingAttribute** or **OnDeserializedAttribute** attribute to the method.</span></span>

<span data-ttu-id="26cf2-158">El ejemplo siguiente muestra el método en el contexto de un tipo.</span><span class="sxs-lookup"><span data-stu-id="26cf2-158">The following example shows the method in the context of a type.</span></span> <span data-ttu-id="26cf2-159">Si una versión anterior de una aplicación envía una instancia de la clase `Address` a una versión posterior de la aplicación, faltarán los datos de campo `CountryField`.</span><span class="sxs-lookup"><span data-stu-id="26cf2-159">If an earlier version of an application sends an instance of the `Address` class to a later version of the application, the `CountryField` field data will be missing.</span></span> <span data-ttu-id="26cf2-160">Pero después de la deserialización, el campo se establecerá en el valor predeterminado "Japan".</span><span class="sxs-lookup"><span data-stu-id="26cf2-160">But after deserialization, the field will be set to a default value "Japan".</span></span>

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

## <a name="the-versionadded-property"></a><span data-ttu-id="26cf2-161">Propiedad VersionAdded</span><span class="sxs-lookup"><span data-stu-id="26cf2-161">The VersionAdded property</span></span>

<span data-ttu-id="26cf2-162">**OptionalFieldAttribute** tiene la propiedad **VersionAdded**.</span><span class="sxs-lookup"><span data-stu-id="26cf2-162">The **OptionalFieldAttribute** has the **VersionAdded** property.</span></span> <span data-ttu-id="26cf2-163">La propiedad indica qué versión de un tipo de un campo determinado se ha agregado.</span><span class="sxs-lookup"><span data-stu-id="26cf2-163">The property indicates which version of a type a given field has been added.</span></span> <span data-ttu-id="26cf2-164">Se debería incrementar en uno exactamente (comenzando en 2) cada vez que se modifica el tipo, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="26cf2-164">It should be incremented by exactly one (starting at 2) every time the type is modified, as shown in the following example:</span></span>

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

## <a name="serializationbinder"></a><span data-ttu-id="26cf2-165">SerializationBinder</span><span class="sxs-lookup"><span data-stu-id="26cf2-165">SerializationBinder</span></span>

<span data-ttu-id="26cf2-166">Algunos usuarios pueden necesitar controlar qué clase serializar y deserializar porque se necesita una versión diferente de la clase en el servidor y el cliente.</span><span class="sxs-lookup"><span data-stu-id="26cf2-166">Some users may need to control which class to serialize and deserialize because a different version of the class is required on the server and client.</span></span> <span data-ttu-id="26cf2-167"><xref:System.Runtime.Serialization.SerializationBinder> es una clase abstracta usada para controlar los tipos reales empleados durante la serialización y la deserialización.</span><span class="sxs-lookup"><span data-stu-id="26cf2-167"><xref:System.Runtime.Serialization.SerializationBinder> is an abstract class used to control the actual types used during serialization and deserialization.</span></span> <span data-ttu-id="26cf2-168">Para usar esta clase, obtenga una clase de <xref:System.Runtime.Serialization.SerializationBinder> y omita los métodos <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> y <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A>.</span><span class="sxs-lookup"><span data-stu-id="26cf2-168">To use this class, derive a class from <xref:System.Runtime.Serialization.SerializationBinder> and override the <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> and <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> methods.</span></span> <span data-ttu-id="26cf2-169">Para obtener más información, vea [Control de la serialización y la deserialización con SerializationBinder](../../framework/wcf/feature-details/controlling-serialization-and-deserialization-with-serializationbinder.md).</span><span class="sxs-lookup"><span data-stu-id="26cf2-169">For more information, see [Controlling Serialization and Deserialization with SerializationBinder](../../framework/wcf/feature-details/controlling-serialization-and-deserialization-with-serializationbinder.md).</span></span>

## <a name="best-practices"></a><span data-ttu-id="26cf2-170">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="26cf2-170">Best practices</span></span>

<span data-ttu-id="26cf2-171">Para asegurar el comportamiento apropiado de la versión, siga estas reglas al modificar un tipo de la versión para la versión:</span><span class="sxs-lookup"><span data-stu-id="26cf2-171">To ensure proper versioning behavior, follow these rules when modifying a type from version to version:</span></span>

- <span data-ttu-id="26cf2-172">Nunca quite un campo serializado.</span><span class="sxs-lookup"><span data-stu-id="26cf2-172">Never remove a serialized field.</span></span>
- <span data-ttu-id="26cf2-173">Nunca aplique el atributo <xref:System.NonSerializedAttribute> a un campo si el atributo no se aplicó al campo en la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="26cf2-173">Never apply the <xref:System.NonSerializedAttribute> attribute to a field if the attribute was not applied to the field in the previous version.</span></span>
- <span data-ttu-id="26cf2-174">Nunca cambie el nombre o el tipo de un campo serializado.</span><span class="sxs-lookup"><span data-stu-id="26cf2-174">Never change the name or the type of a serialized field.</span></span>
- <span data-ttu-id="26cf2-175">Al agregar un nuevo campo serializado, aplique el atributo **OptionalFieldAttribute**.</span><span class="sxs-lookup"><span data-stu-id="26cf2-175">When adding a new serialized field, apply the **OptionalFieldAttribute** attribute.</span></span>
- <span data-ttu-id="26cf2-176">Al quitar un atributo **NonSerializedAttribute** de un campo (que no era serializable en una versión anterior), aplique el atributo **OptionalFieldAttribute**.</span><span class="sxs-lookup"><span data-stu-id="26cf2-176">When removing a **NonSerializedAttribute** attribute from a field (that was not serializable in a previous version), apply the **OptionalFieldAttribute** attribute.</span></span>
- <span data-ttu-id="26cf2-177">Para todos los campos opcionales, establezca valores predeterminados significativos mediante las devoluciones de llamada de serialización, a menos que se acepten 0 o **null** como valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="26cf2-177">For all optional fields, set meaningful defaults using the serialization callbacks unless 0 or **null** as defaults are acceptable.</span></span>

<span data-ttu-id="26cf2-178">Para asegurarse de que un tipo será compatible con motores de serialización futuros, siga estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="26cf2-178">To ensure that a type will be compatible with future serialization engines, follow these guidelines:</span></span>

- <span data-ttu-id="26cf2-179">Establezca siempre correctamente la propiedad **VersionAdded** en el atributo **OptionalFieldAttribute**.</span><span class="sxs-lookup"><span data-stu-id="26cf2-179">Always set the **VersionAdded** property on the **OptionalFieldAttribute** attribute correctly.</span></span>
- <span data-ttu-id="26cf2-180">Evite la versión bifurcada.</span><span class="sxs-lookup"><span data-stu-id="26cf2-180">Avoid branched versioning.</span></span>

## <a name="see-also"></a><span data-ttu-id="26cf2-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="26cf2-181">See also</span></span>

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
- [<span data-ttu-id="26cf2-182">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="26cf2-182">Binary Serialization</span></span>](binary-serialization.md)
