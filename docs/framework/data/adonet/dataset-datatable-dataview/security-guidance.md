---
description: 'Más información sobre: instrucciones de seguridad de DataSet y DataTable'
title: Guía de seguridad de DataSet y DataTable
ms.date: 07/14/2020
dev_langs:
- csharp
ms.openlocfilehash: ec0130d5b5ad106cc3a0a26b45ebff34f73e31d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651644"
---
# <a name="dataset-and-datatable-security-guidance"></a><span data-ttu-id="45ab9-103">Guía de seguridad de DataSet y DataTable</span><span class="sxs-lookup"><span data-stu-id="45ab9-103">DataSet and DataTable security guidance</span></span>

<span data-ttu-id="45ab9-104">Este artículo se aplica a:</span><span class="sxs-lookup"><span data-stu-id="45ab9-104">This article applies to:</span></span>

* <span data-ttu-id="45ab9-105">.NET Framework (todas las versiones)</span><span class="sxs-lookup"><span data-stu-id="45ab9-105">.NET Framework (all versions)</span></span>
* <span data-ttu-id="45ab9-106">.NET Core y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="45ab9-106">.NET Core and later</span></span>
* <span data-ttu-id="45ab9-107">.NET 5.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="45ab9-107">.NET 5.0 and later</span></span>

<span data-ttu-id="45ab9-108">Los tipos [DataSet](/dotnet/api/system.data.dataset) y [DataTable](/dotnet/api/system.data.datatable) son componentes de .net heredados que permiten representar conjuntos de datos como objetos administrados.</span><span class="sxs-lookup"><span data-stu-id="45ab9-108">The [DataSet](/dotnet/api/system.data.dataset) and [DataTable](/dotnet/api/system.data.datatable) types are legacy .NET components that allow representing data sets as managed objects.</span></span> <span data-ttu-id="45ab9-109">Estos componentes se introdujeron en .NET Framework 1,0 como parte de la [infraestructura de ADO.net](./index.md)original.</span><span class="sxs-lookup"><span data-stu-id="45ab9-109">These components were introduced in .NET Framework 1.0 as part of the original [ADO.NET infrastructure](./index.md).</span></span> <span data-ttu-id="45ab9-110">Su objetivo era proporcionar una vista administrada a través de un conjunto de datos relacional, extraabstraendo si el origen subyacente de los datos era XML, SQL u otra tecnología.</span><span class="sxs-lookup"><span data-stu-id="45ab9-110">Their goal was to provide a managed view over a relational data set, abstracting away whether the underlying source of the data was XML, SQL, or another technology.</span></span>

<span data-ttu-id="45ab9-111">Para obtener más información sobre ADO.NET, incluidos los paradigmas más modernos de la vista de datos, vea [la documentación de ADO.net](../index.md).</span><span class="sxs-lookup"><span data-stu-id="45ab9-111">For more information on ADO.NET, including more modern data view paradigms, see [the ADO.NET documentation](../index.md).</span></span>

## <a name="default-restrictions-when-deserializing-a-dataset-or-datatable-from-xml"></a><span data-ttu-id="45ab9-112">Restricciones predeterminadas al deserializar un DataSet o DataTable desde XML</span><span class="sxs-lookup"><span data-stu-id="45ab9-112">Default restrictions when deserializing a DataSet or DataTable from XML</span></span>

<span data-ttu-id="45ab9-113">En todas las versiones compatibles de .NET Framework, .NET Core y .NET, `DataSet` y `DataTable` se aplican las restricciones siguientes a los tipos de objetos que pueden estar presentes en los datos deserializados.</span><span class="sxs-lookup"><span data-stu-id="45ab9-113">On all supported versions of .NET Framework, .NET Core, and .NET, `DataSet` and `DataTable` place the following restrictions on what types of objects may be present in the deserialized data.</span></span> <span data-ttu-id="45ab9-114">De forma predeterminada, esta lista está restringida a:</span><span class="sxs-lookup"><span data-stu-id="45ab9-114">By default, this list is restricted to:</span></span>

* <span data-ttu-id="45ab9-115">Tipos primitivos y equivalentes primitivos:,,,,,,,,,,,,,,,,,,, `bool` `char` `sbyte` `byte` `short` `ushort` `int` `uint` `long` `ulong` `float` `double` `decimal` `DateTime` `DateTimeOffset` `TimeSpan` `string` `Guid` `SqlBinary` `SqlBoolean` , `SqlByte` , `SqlBytes` ,,,, `SqlChars` , `SqlDateTime` `SqlDecimal` `SqlDouble` `SqlGuid` `SqlInt16` `SqlInt32` `SqlInt64` `SqlMoney` `SqlSingle` `SqlString` ,,,,, y.</span><span class="sxs-lookup"><span data-stu-id="45ab9-115">Primitives and primitive equivalents: `bool`, `char`, `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, `decimal`, `DateTime`, `DateTimeOffset`, `TimeSpan`, `string`, `Guid`, `SqlBinary`, `SqlBoolean`, `SqlByte`, `SqlBytes`, `SqlChars`, `SqlDateTime`, `SqlDecimal`, `SqlDouble`, `SqlGuid`, `SqlInt16`, `SqlInt32`, `SqlInt64`, `SqlMoney`, `SqlSingle`, and `SqlString`.</span></span>
* <span data-ttu-id="45ab9-116">No primitivos usados comúnmente: `Type` , `Uri` y `BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="45ab9-116">Commonly used non-primitives: `Type`, `Uri`, and `BigInteger`.</span></span>
* <span data-ttu-id="45ab9-117">Tipos _System. Drawing_ usados comúnmente: `Color` , `Point` , `PointF` , `Rectangle` , `RectangleF` , `Size` y `SizeF` .</span><span class="sxs-lookup"><span data-stu-id="45ab9-117">Commonly used _System.Drawing_ types: `Color`, `Point`, `PointF`, `Rectangle`, `RectangleF`, `Size`, and `SizeF`.</span></span>
* <span data-ttu-id="45ab9-118">`Enum` distintos.</span><span class="sxs-lookup"><span data-stu-id="45ab9-118">`Enum` types.</span></span>
* <span data-ttu-id="45ab9-119">Matrices y listas de los tipos anteriores.</span><span class="sxs-lookup"><span data-stu-id="45ab9-119">Arrays and lists of the above types.</span></span>

<span data-ttu-id="45ab9-120">Si los datos XML entrantes contienen un objeto cuyo tipo no está en esta lista:</span><span class="sxs-lookup"><span data-stu-id="45ab9-120">If the incoming XML data contains an object whose type is not in this list:</span></span>

* <span data-ttu-id="45ab9-121">Se produce una excepción con el siguiente mensaje y seguimiento de la pila.</span><span class="sxs-lookup"><span data-stu-id="45ab9-121">An exception is thrown with the following message and stack trace.</span></span>
<span data-ttu-id="45ab9-122">Mensaje de error: System. InvalidOperationException: type ' \<Type Name\> , version = \<n.n.n.n\> , Culture = \<culture\> , PublicKeyToken = \<token value\> ' no se permite aquí.</span><span class="sxs-lookup"><span data-stu-id="45ab9-122">Error Message: System.InvalidOperationException : Type '\<Type Name\>, Version=\<n.n.n.n\>, Culture=\<culture\>, PublicKeyToken=\<token value\>' is not allowed here.</span></span> <span data-ttu-id="45ab9-123">Para más información, consulte [https://go.microsoft.com/fwlink/?linkid=2132227](https://go.microsoft.com/fwlink/?linkid=2132227).</span><span class="sxs-lookup"><span data-stu-id="45ab9-123">See [https://go.microsoft.com/fwlink/?linkid=2132227](https://go.microsoft.com/fwlink/?linkid=2132227) for more details.</span></span>
<span data-ttu-id="45ab9-124">Seguimiento de la pila: en System. Data. TypeLimiter. EnsureTypeIsAllowed (tipo Type, TypeLimiter capturedLimiter) en System. Data. DataColumn. UpdateColumnType (Type Type, StorageType typeCode) en System.Data.DataColumn.set_DataType (tipo Value)</span><span class="sxs-lookup"><span data-stu-id="45ab9-124">Stack Trace: at System.Data.TypeLimiter.EnsureTypeIsAllowed(Type type, TypeLimiter capturedLimiter) at System.Data.DataColumn.UpdateColumnType(Type type, StorageType typeCode) at System.Data.DataColumn.set_DataType(Type value)</span></span>

* <span data-ttu-id="45ab9-125">Se produce un error en la operación de deserialización.</span><span class="sxs-lookup"><span data-stu-id="45ab9-125">The deserialization operation fails.</span></span>

<span data-ttu-id="45ab9-126">Al cargar XML en una `DataSet` instancia de o existente `DataTable` , también se tienen en cuenta las definiciones de columna existentes.</span><span class="sxs-lookup"><span data-stu-id="45ab9-126">When loading XML into an existing `DataSet` or `DataTable` instance, the existing column definitions are also taken into account.</span></span> <span data-ttu-id="45ab9-127">Si la tabla ya contiene una definición de columna de un tipo personalizado, ese tipo se agrega temporalmente a la lista de permitidos mientras dure la operación de deserialización de XML.</span><span class="sxs-lookup"><span data-stu-id="45ab9-127">If the table already contains a column definition of a custom type, that type is temporarily added to the allow list for the duration of the XML deserialization operation.</span></span>

> [!NOTE]
> <span data-ttu-id="45ab9-128">Una vez que se agregan columnas a `DataTable` , `ReadXml` no se leerá el esquema del XML y, si el esquema no coincide, tampoco se leerán en los registros, por lo que tendrá que agregar todas las columnas para usar este método.</span><span class="sxs-lookup"><span data-stu-id="45ab9-128">Once you add columns to a `DataTable`, `ReadXml` will not read the schema from the XML, and if the schema does not match it will also not read in the records, so you will need to add all the columns yourself to use this method.</span></span>

```csharp
XmlReader xmlReader = GetXmlReader();

// Assume the XML blob contains data for type MyCustomClass.
// The following call to ReadXml fails because MyCustomClass isn't in the allowed types list.

DataTable table = new DataTable("MyDataTable");
table.ReadXml(xmlReader);

// However, the following call to ReadXml succeeds, since the DataTable instance
// already defines a column of type MyCustomClass.

DataTable table = new DataTable("MyDataTable");
table.Columns.Add("MyColumn", typeof(MyCustomClass));
table.ReadXml(xmlReader); // this call will succeed
```

<span data-ttu-id="45ab9-129">Las restricciones de tipo de objeto también se aplican cuando `XmlSerializer` se usa para deserializar una instancia de `DataSet` o `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="45ab9-129">The object type restrictions also apply when using `XmlSerializer` to deserialize an instance of `DataSet` or `DataTable`.</span></span> <span data-ttu-id="45ab9-130">Sin embargo, es posible que no se apliquen al utilizar `BinaryFormatter` para deserializar una instancia de `DataSet` o `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="45ab9-130">However, they may not apply when using `BinaryFormatter` to deserialize an instance of `DataSet` or `DataTable`.</span></span>

<span data-ttu-id="45ab9-131">Las restricciones de tipo de objeto no se aplican cuando `DataAdapter.Fill` se usa, como cuando una `DataTable` instancia se rellena directamente desde una base de datos sin usar las API de deserialización XML.</span><span class="sxs-lookup"><span data-stu-id="45ab9-131">The object type restrictions don't apply when using `DataAdapter.Fill`, such as when a `DataTable` instance is populated directly from a database without using the XML deserialization APIs.</span></span>

### <a name="extend-the-list-of-allowed-types"></a><span data-ttu-id="45ab9-132">Ampliar la lista de tipos permitidos</span><span class="sxs-lookup"><span data-stu-id="45ab9-132">Extend the list of allowed types</span></span>

<span data-ttu-id="45ab9-133">Una aplicación puede extender la lista de tipos permitidos para incluir tipos personalizados además de los tipos integrados enumerados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="45ab9-133">An app can extend the allowed types list to include custom types in addition to the built-in types listed above.</span></span> <span data-ttu-id="45ab9-134">Si se extiende la lista de tipos permitidos, el cambio afecta a _todas_ las `DataSet` instancias de y dentro de `DataTable` la aplicación.</span><span class="sxs-lookup"><span data-stu-id="45ab9-134">If extending the allowed types list, the change affects _all_ `DataSet` and `DataTable` instances within the app.</span></span> <span data-ttu-id="45ab9-135">Los tipos no se pueden quitar de la lista de tipos permitidos integrados.</span><span class="sxs-lookup"><span data-stu-id="45ab9-135">Types cannot be removed from the built-in allowed types list.</span></span>

#### <a name="extend-through-configuration-net-framework-40---48"></a><span data-ttu-id="45ab9-136">Extender a través de la configuración (.NET Framework 4,0-4,8)</span><span class="sxs-lookup"><span data-stu-id="45ab9-136">Extend through configuration (.NET Framework 4.0 - 4.8)</span></span>

<span data-ttu-id="45ab9-137">_App.config_ se puede usar para ampliar la lista de tipos permitidos.</span><span class="sxs-lookup"><span data-stu-id="45ab9-137">_App.config_ can be used to extend the allowed types list.</span></span> <span data-ttu-id="45ab9-138">Para ampliar la lista de tipos permitidos:</span><span class="sxs-lookup"><span data-stu-id="45ab9-138">To extend the allowed types list:</span></span>

* <span data-ttu-id="45ab9-139">Use el `<configSections>` elemento para agregar una referencia a la sección de configuración _System. Data_ .</span><span class="sxs-lookup"><span data-stu-id="45ab9-139">Use the `<configSections>` element to add a reference to the _System.Data_ configuration section.</span></span>
* <span data-ttu-id="45ab9-140">`<system.data.dataset.serialization>` / `<allowedTypes>` Se usa para especificar tipos adicionales.</span><span class="sxs-lookup"><span data-stu-id="45ab9-140">Use `<system.data.dataset.serialization>`/`<allowedTypes>` to specify additional types.</span></span>

<span data-ttu-id="45ab9-141">Cada `<add>` elemento debe especificar un solo tipo usando su nombre de tipo calificado con el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="45ab9-141">Each `<add>` element must specify only one type by using its assembly qualified type name.</span></span> <span data-ttu-id="45ab9-142">Para agregar tipos adicionales a la lista de tipos permitidos, use varios `<add>` elementos.</span><span class="sxs-lookup"><span data-stu-id="45ab9-142">To add additional types to the allowed types list, use multiple `<add>` elements.</span></span>

<span data-ttu-id="45ab9-143">En el ejemplo siguiente se muestra cómo extender la lista de tipos permitidos agregando el tipo personalizado `Fabrikam.CustomType` .</span><span class="sxs-lookup"><span data-stu-id="45ab9-143">The following sample shows extending the allowed types list by adding the custom type `Fabrikam.CustomType`.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add type="assembly qualified type name" /> -->
      <add type="Fabrikam.CustomType, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
      <!-- additional <add /> elements as needed -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

<span data-ttu-id="45ab9-144">Para recuperar el nombre calificado del ensamblado de un tipo, use la propiedad [Type. AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) , como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="45ab9-144">To retrieve the assembly qualified name of a type, use the [Type.AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) property, as demonstrated in the following code.</span></span>

```csharp
string assemblyQualifiedName = typeof(Fabrikam.CustomType).AssemblyQualifiedName;
```

<a name="etc"></a>

#### <a name="extend-through-configuration-net-framework-20---35"></a><span data-ttu-id="45ab9-145">Extender a través de la configuración (.NET Framework 2,0-3,5)</span><span class="sxs-lookup"><span data-stu-id="45ab9-145">Extend through configuration (.NET Framework 2.0 - 3.5)</span></span>

<span data-ttu-id="45ab9-146">Si su aplicación tiene como destino .NET Framework 2,0 o 3,5, todavía puede usar el mecanismo de _App.config_ anterior para ampliar la lista de tipos permitidos.</span><span class="sxs-lookup"><span data-stu-id="45ab9-146">If your app targets .NET Framework 2.0 or 3.5, you can still use the above _App.config_ mechanism to extend the allowed types list.</span></span> <span data-ttu-id="45ab9-147">Sin embargo, el `<configSections>` elemento tendrá un aspecto ligeramente diferente, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ab9-147">However, your `<configSections>` element will look slightly different, as shown in the following code:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- The below <sectionGroup> and <section> are specific to .NET Framework 2.0 and 3.5. -->
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add /> elements, as demonstrated in the .NET Framework 4.0 - 4.8 sample code above. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

#### <a name="extend-programmatically-net-framework-net-core-net-50"></a><span data-ttu-id="45ab9-148">Extender mediante programación (.NET Framework, .NET Core, .NET 5.0 +)</span><span class="sxs-lookup"><span data-stu-id="45ab9-148">Extend programmatically (.NET Framework, .NET Core, .NET 5.0+)</span></span>

<span data-ttu-id="45ab9-149">La lista de tipos permitidos también puede ampliarse mediante programación usando [AppDomain. SetData](/dotnet/api/system.appdomain.setdata) con el sistema de claves conocido _System. Data. DataSetDefaultAllowedTypes_, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="45ab9-149">The list of allowed types can also be extended programmatically by using [AppDomain.SetData](/dotnet/api/system.appdomain.setdata) with the well-known key _System.Data.DataSetDefaultAllowedTypes_, as shown in the following code.</span></span>

```csharp
Type[] extraAllowedTypes = new Type[]
{
    typeof(Fabrikam.CustomType),
    typeof(Contoso.AdditionalCustomType)
};

AppDomain.CurrentDomain.SetData("System.Data.DataSetDefaultAllowedTypes", extraAllowedTypes);
```

<span data-ttu-id="45ab9-150">Si se usa el mecanismo de extensión, el valor asociado a la clave _System. Data. DataSetDefaultAllowedTypes_ debe ser de tipo `Type[]` .</span><span class="sxs-lookup"><span data-stu-id="45ab9-150">If using the extension mechanism, the value associated with the key _System.Data.DataSetDefaultAllowedTypes_ must be of type `Type[]`.</span></span>

<span data-ttu-id="45ab9-151">En .NET Framework, la lista de tipos permitidos se puede extender con _App.config_ y `AppDomain.SetData` .</span><span class="sxs-lookup"><span data-stu-id="45ab9-151">On .NET Framework, the list of allowed types may be extended both with _App.config_ and `AppDomain.SetData`.</span></span> <span data-ttu-id="45ab9-152">En este caso, `DataSet` y `DataTable` permitirá que un objeto se deserialice como parte de los datos si su tipo está presente en cualquiera de las listas.</span><span class="sxs-lookup"><span data-stu-id="45ab9-152">In this case, `DataSet` and `DataTable` will allow an object to be deserialized as part of the data if its type is present in either list.</span></span>

### <a name="run-an-app-in-audit-mode-net-framework"></a><span data-ttu-id="45ab9-153">Ejecutar una aplicación en modo auditoría (.NET Framework)</span><span class="sxs-lookup"><span data-stu-id="45ab9-153">Run an app in audit mode (.NET Framework)</span></span>

<span data-ttu-id="45ab9-154">En .NET Framework, `DataSet` y `DataTable` proporcionan una capacidad de modo de auditoría.</span><span class="sxs-lookup"><span data-stu-id="45ab9-154">In .NET Framework, `DataSet` and `DataTable` provide an audit mode capability.</span></span> <span data-ttu-id="45ab9-155">Cuando está habilitado el modo `DataSet` de auditoría y `DataTable` compara los tipos de objetos entrantes con la lista de tipos permitidos.</span><span class="sxs-lookup"><span data-stu-id="45ab9-155">When audit mode is enabled, `DataSet` and `DataTable` compare the types of incoming objects against the allowed types list.</span></span> <span data-ttu-id="45ab9-156">Sin embargo, si se muestra un objeto cuyo tipo no está permitido, **no** se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="45ab9-156">However, if an object whose type is not allowed is seen, an exception is **not** thrown.</span></span> <span data-ttu-id="45ab9-157">En su lugar, `DataSet` y `DataTable` notifican a las instancias adjuntas `TraceListener` que un tipo sospechoso está presente, lo que permite `TraceListener` que registre esta información.</span><span class="sxs-lookup"><span data-stu-id="45ab9-157">Instead, `DataSet` and `DataTable` notify any attached `TraceListener` instances that a suspicious type is present, allowing the `TraceListener` to log this information.</span></span> <span data-ttu-id="45ab9-158">No se produce ninguna excepción y continúa la operación de deserialización.</span><span class="sxs-lookup"><span data-stu-id="45ab9-158">No exception is thrown and the deserialization operation continues.</span></span>

> [!WARNING]
> <span data-ttu-id="45ab9-159">La ejecución de una aplicación en "modo de auditoría" solo debe ser una medida temporal utilizada para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="45ab9-159">Running an app in "audit mode" should only be a temporary measure used for testing.</span></span> <span data-ttu-id="45ab9-160">Cuando el modo de auditoría está habilitado `DataSet` y `DataTable` no impone restricciones de tipo, lo que puede incluir un hueco de seguridad dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="45ab9-160">When audit mode is enabled, `DataSet` and `DataTable` do not enforce type restrictions, which can introduce a security hole inside your app.</span></span> <span data-ttu-id="45ab9-161">Para obtener más información, vea las secciones titulada [quitar todas las restricciones de tipo](#ratr) y [seguridad con respecto a la entrada que](#swr)no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="45ab9-161">For more information, see the sections titled [Removing all type restrictions](#ratr) and [Safety with regard to untrusted input](#swr).</span></span>

<span data-ttu-id="45ab9-162">El modo auditoría se puede habilitar a través de _App.config_:</span><span class="sxs-lookup"><span data-stu-id="45ab9-162">Audit mode can be enabled through _App.config_:</span></span>

* <span data-ttu-id="45ab9-163">Vea la sección [extender a través](#etc) de la configuración de este documento para obtener información sobre el valor apropiado que se debe colocar para el `<configSections>` elemento.</span><span class="sxs-lookup"><span data-stu-id="45ab9-163">See the [Extending through configuration](#etc) section in this document for information on the proper value to put for the `<configSections>` element.</span></span>
* <span data-ttu-id="45ab9-164">Use `<allowedTypes auditOnly="true">` para habilitar el modo de auditoría, tal como se muestra en el marcado siguiente.</span><span class="sxs-lookup"><span data-stu-id="45ab9-164">Use `<allowedTypes auditOnly="true">` to enable audit mode, as shown in the following markup.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- See the section of this document titled "Extending through configuration" for the appropriate
         <sectionGroup> and <section> elements to put here, depending on whether you're running .NET
         Framework 2.0 - 3.5 or 4.0 - 4.8. -->
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes auditOnly="true"> <!-- setting auditOnly="true" enables audit mode -->
      <!-- Optional <add /> elements as needed. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

<span data-ttu-id="45ab9-165">Una vez habilitado el modo de auditoría, puede usar _App.config_ para conectar su preferido `TraceListener` al `DataSet` nombre integrado del `TraceSource.` origen de seguimiento integrado es _System. Data. DataSet_.</span><span class="sxs-lookup"><span data-stu-id="45ab9-165">Once audit mode is enabled, you can use _App.config_ to connect your preferred `TraceListener` to the `DataSet` built-in `TraceSource.` The name of the built-in trace source is _System.Data.DataSet_.</span></span> <span data-ttu-id="45ab9-166">En el ejemplo siguiente se muestra cómo escribir eventos de seguimiento en la consola _y_ en un archivo de registro en disco.</span><span class="sxs-lookup"><span data-stu-id="45ab9-166">The following sample demonstrates writing trace events to the console _and_ to a log file on disk.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.Data.DataSet"
              switchType="System.Diagnostics.SourceSwitch"
              switchValue="Warning">
        <listeners>
          <!-- write to the console -->
          <add name="console"
               type="System.Diagnostics.ConsoleTraceListener" />
          <!-- *and* write to a log file on disk -->
          <add name="filelog"
               type="System.Diagnostics.TextWriterTraceListener"
               initializeData="c:\logs\mylog.txt" />
        </listeners>
      </source>
    </sources>
  </system.diagnostics>
</configuration>
```

<span data-ttu-id="45ab9-167">Para obtener más información sobre `TraceSource` y `TraceListener` , vea el documento [Cómo: utilizar TraceSource y filtros con agentes de escucha de seguimiento](../../../debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="45ab9-167">For more information on `TraceSource` and `TraceListener`, see the document [How to: Use TraceSource and Filters with Trace Listeners](../../../debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md).</span></span>

> [!NOTE]
> <span data-ttu-id="45ab9-168">La ejecución de una aplicación en modo auditoría no está disponible en .NET Core o en .NET 5,0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="45ab9-168">Running an app in audit mode is not available in .NET Core or in .NET 5.0 and later.</span></span>

<a name="ratr"></a>

### <a name="remove-all-type-restrictions"></a><span data-ttu-id="45ab9-169">Quitar todas las restricciones de tipo</span><span class="sxs-lookup"><span data-stu-id="45ab9-169">Remove all type restrictions</span></span>

<span data-ttu-id="45ab9-170">Si una aplicación debe quitar todas las restricciones de limitación de tipos de `DataSet` y `DataTable` :</span><span class="sxs-lookup"><span data-stu-id="45ab9-170">If an app must remove all type limiting restrictions from `DataSet` and `DataTable`:</span></span>

* <span data-ttu-id="45ab9-171">Hay varias opciones para suprimir las restricciones de limitación de tipos.</span><span class="sxs-lookup"><span data-stu-id="45ab9-171">There are several options to suppress type limiting restrictions.</span></span>
* <span data-ttu-id="45ab9-172">Las opciones disponibles dependen del marco de trabajo de destino de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="45ab9-172">The options available depend on the framework the app targets.</span></span>

> [!WARNING]
> <span data-ttu-id="45ab9-173">Al quitar todas las restricciones de tipo, se puede introducir un agujero de seguridad dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="45ab9-173">Removing all type restrictions can introduce a security hole inside the app.</span></span> <span data-ttu-id="45ab9-174">Al utilizar este mecanismo, asegúrese de que la  aplicación no usa `DataSet` o `DataTable` para leer la entrada que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="45ab9-174">When using this mechanism, ensure the app does **not** use `DataSet` or `DataTable` to read untrusted input.</span></span> <span data-ttu-id="45ab9-175">Para obtener más información, vea [CVE-2020-1147](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/CVE-2020-1147) y la sección siguiente titulada [seguridad con respecto a la entrada que no es de confianza](#swr).</span><span class="sxs-lookup"><span data-stu-id="45ab9-175">For more information, see [CVE-2020-1147](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/CVE-2020-1147) and the following section titled [Safety with regard to untrusted input](#swr).</span></span>

#### <a name="through-appcontext-configuration-net-framework-46---48-net-core-21-and-later-net-50-and-later"></a><span data-ttu-id="45ab9-176">A través de la configuración de AppContext (.NET Framework 4,6-4,8, .NET Core 2,1 y versiones posteriores, .NET 5,0 y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="45ab9-176">Through AppContext configuration (.NET Framework 4.6 - 4.8, .NET Core 2.1 and later, .NET 5.0 and later)</span></span>

<span data-ttu-id="45ab9-177">El `AppContext` modificador, `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` , cuando se establece en, `true` quita todas las restricciones de limitación de tipos de `DataSet` y `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="45ab9-177">The `AppContext` switch, `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation`, when set to `true` removes all type limiting restrictions from `DataSet` and `DataTable`.</span></span>

<span data-ttu-id="45ab9-178">En .NET Framework, este modificador se puede habilitar a través de _App.config_, tal y como se muestra en la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ab9-178">In .NET Framework, this switch can be enabled via _App.config_, as shown in the following configuration:</span></span>

```xml
<configuration>
   <runtime>
      <!-- Warning: setting the following switch can introduce a security problem. -->
      <AppContextSwitchOverrides value="Switch.System.Data.AllowArbitraryDataSetTypeInstantiation=true" />
   </runtime>
</configuration>
```

<span data-ttu-id="45ab9-179">En ASP.NET, el `<AppContextSwitchOverrides>` elemento no está disponible.</span><span class="sxs-lookup"><span data-stu-id="45ab9-179">In ASP.NET, the `<AppContextSwitchOverrides>` element is not available.</span></span> <span data-ttu-id="45ab9-180">En su lugar, el conmutador se puede habilitar a través de _Web.config_, como se muestra en la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ab9-180">Instead, the switch can be enabled via _Web.config_, as shown in the following configuration:</span></span>

```xml
<configuration>
    <appSettings>
        <!-- Warning: setting the following switch can introduce a security problem. -->
        <add key="AppContext.SetSwitch:Switch.System.Data.AllowArbitraryDataSetTypeInstantiation" value="true" />
    </appSettings>
</configuration>
```

<span data-ttu-id="45ab9-181">Para obtener más información, vea el [\<AppContextSwitchOverrides>](../../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="45ab9-181">For more information, see the [\<AppContextSwitchOverrides>](../../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element.</span></span>

<span data-ttu-id="45ab9-182">En .NET Core, .NET 5 y ASP.NET Core, este valor se controla mediante _runtimeconfig.jsen_, tal y como se muestra en el siguiente JSON:</span><span class="sxs-lookup"><span data-stu-id="45ab9-182">In .NET Core, .NET 5, and ASP.NET Core, this setting is controlled by _runtimeconfig.json_, as shown in the following JSON:</span></span>

```json
{
  "runtimeOptions": {
    "configProperties": {
      "Switch.System.Data.AllowArbitraryDataSetTypeInstantiation": true
    }
  }
}
```

<span data-ttu-id="45ab9-183">Para obtener más información, vea ["opciones de configuración en tiempo de ejecución de .net Core"](../../../../core/run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="45ab9-183">For more information, see [".NET Core run-time configuration settings"](../../../../core/run-time-config/index.md).</span></span>

<span data-ttu-id="45ab9-184">`AllowArbitraryDataSetTypeInstantiation` también se puede establecer mediante programación a través de [AppContext. SetSwitch](/dotnet/api/system.appcontext.setswitch) en lugar de usar un archivo de configuración, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ab9-184">`AllowArbitraryDataSetTypeInstantiation` can also be set programmatically via [AppContext.SetSwitch](/dotnet/api/system.appcontext.setswitch) instead of using a configuration file, as shown in the following code:</span></span>

```csharp
// Warning: setting the following switch can introduce a security problem.
AppContext.SetSwitch("Switch.System.Data.AllowArbitraryDataSetTypeInstantiation", true);
```

 <span data-ttu-id="45ab9-185">Si elige el enfoque de programación anterior, la llamada a `AppContext.SetSwitch` debe realizarse al principio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="45ab9-185">If you choose the preceding programmatic approach, the call to `AppContext.SetSwitch` should occur early in the apps startup.</span></span>

#### <a name="through-the-machine-wide-registry-net-framework-20---48"></a><span data-ttu-id="45ab9-186">A través del registro en todo el equipo (.NET Framework 2,0-4,8)</span><span class="sxs-lookup"><span data-stu-id="45ab9-186">Through the machine-wide registry (.NET Framework 2.0 - 4.8)</span></span>

<span data-ttu-id="45ab9-187">Si `AppContext` no está disponible, las comprobaciones de limitación de tipos se pueden deshabilitar con el registro de Windows:</span><span class="sxs-lookup"><span data-stu-id="45ab9-187">If `AppContext` is not available, type limiting checks can be disabled with the Windows registry:</span></span>

* <span data-ttu-id="45ab9-188">Un administrador debe configurar el registro.</span><span class="sxs-lookup"><span data-stu-id="45ab9-188">An administrator must configure the registry.</span></span>
* <span data-ttu-id="45ab9-189">El uso del registro es un cambio en todo el equipo y afectará a _todas las_ aplicaciones que se ejecutan en la máquina.</span><span class="sxs-lookup"><span data-stu-id="45ab9-189">Using the registry is a machine-wide change and will affect _all_ apps running on the machine.</span></span>

| <span data-ttu-id="45ab9-190">Tipo</span><span class="sxs-lookup"><span data-stu-id="45ab9-190">Type</span></span>  |  <span data-ttu-id="45ab9-191">Value</span><span class="sxs-lookup"><span data-stu-id="45ab9-191">Value</span></span> |
|---|---|
| <span data-ttu-id="45ab9-192">**Clave del Registro**</span><span class="sxs-lookup"><span data-stu-id="45ab9-192">**Registry key**</span></span> | `HKLM\SOFTWARE\Microsoft\.NETFramework\AppContext` |
| <span data-ttu-id="45ab9-193">**Nombre del valor**</span><span class="sxs-lookup"><span data-stu-id="45ab9-193">**Value name**</span></span> | `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` |
| <span data-ttu-id="45ab9-194">**Tipo de valor**</span><span class="sxs-lookup"><span data-stu-id="45ab9-194">**Value type**</span></span> | `REG_SZ` |
| <span data-ttu-id="45ab9-195">**Datos de valor**</span><span class="sxs-lookup"><span data-stu-id="45ab9-195">**Value data**</span></span> | `true` |

<span data-ttu-id="45ab9-196">En un sistema operativo de 64 bits, es necesario agregar este valor para la clave de 64 bits (mostrada anteriormente) y la clave de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="45ab9-196">On a 64-bit operating system, this value my need to be added for both the 64-bit key (shown above) and the 32-bit key.</span></span> <span data-ttu-id="45ab9-197">La clave de 32 bits se encuentra en `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext` .</span><span class="sxs-lookup"><span data-stu-id="45ab9-197">The 32-bit key is located at `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext`.</span></span>

<span data-ttu-id="45ab9-198">Para obtener más información sobre el uso del registro para configurar `AppContext` , vea ["AppContext for Library Consumers"](/dotnet/api/system.appcontext#appcontext-for-library-consumers).</span><span class="sxs-lookup"><span data-stu-id="45ab9-198">For more information on using the registry to configure `AppContext`, see ["AppContext for library consumers"](/dotnet/api/system.appcontext#appcontext-for-library-consumers).</span></span>

<a name="swr"></a>

## <a name="safety-with-regard-to-untrusted-input"></a><span data-ttu-id="45ab9-199">Seguridad con respecto a la entrada que no es de confianza</span><span class="sxs-lookup"><span data-stu-id="45ab9-199">Safety with regard to untrusted input</span></span>

<span data-ttu-id="45ab9-200">While `DataSet` y `DataTable` imponen limitaciones predeterminadas en los tipos que se pueden encontrar durante la deserialización de cargas XML __`DataSet` y `DataTable` no suelen ser seguras cuando se rellenan con una entrada que no es de confianza.__</span><span class="sxs-lookup"><span data-stu-id="45ab9-200">While `DataSet` and `DataTable` do impose default limitations on the types that are allowed to be present while deserializing XML payloads, __`DataSet` and `DataTable` are in general not safe when populated with untrusted input.__</span></span> <span data-ttu-id="45ab9-201">A continuación se muestra una lista no exhaustiva de formas en que `DataSet` una `DataTable` instancia de o podría leer una entrada que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="45ab9-201">The following is a non-exhaustive list of ways that a `DataSet` or `DataTable` instance might read untrusted input.</span></span>

* <span data-ttu-id="45ab9-202">Un `DataAdapter` hace referencia a una base de datos de y el `DataAdapter.Fill` método se utiliza para rellenar `DataSet` con el contenido de una consulta de base de datos.</span><span class="sxs-lookup"><span data-stu-id="45ab9-202">A `DataAdapter` references a database, and the `DataAdapter.Fill` method is used to populate a `DataSet` with the contents of a database query.</span></span>
* <span data-ttu-id="45ab9-203">El `DataSet.ReadXml` `DataTable.ReadXml` método o se utiliza para leer un archivo XML que contiene información de columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="45ab9-203">The `DataSet.ReadXml` or `DataTable.ReadXml` method is used to read an XML file containing column and row information.</span></span>
* <span data-ttu-id="45ab9-204">Una `DataSet` instancia de o `DataTable` se serializa como parte de un punto de conexión de WCF o servicios Web ASP.net (SOAP).</span><span class="sxs-lookup"><span data-stu-id="45ab9-204">A `DataSet` or `DataTable` instance is serialized as part of a ASP.NET (SOAP) web services or WCF endpoint.</span></span>
* <span data-ttu-id="45ab9-205">Un serializador como `XmlSerializer` se utiliza para deserializar una `DataSet` `DataTable` instancia de o de una secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="45ab9-205">A serializer such as `XmlSerializer` is used to deserialize a `DataSet` or `DataTable` instance from an XML stream.</span></span>
* <span data-ttu-id="45ab9-206">Un serializador como `JsonConvert` se usa para deserializar una `DataSet` `DataTable` instancia de o de un flujo JSON.</span><span class="sxs-lookup"><span data-stu-id="45ab9-206">A serializer such as `JsonConvert` is used to deserialize a `DataSet` or `DataTable` instance from a JSON stream.</span></span> <span data-ttu-id="45ab9-207">`JsonConvert` es un método de la conocida [Newtonsoft.Jsde terceros en](https://www.newtonsoft.com/json) la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="45ab9-207">`JsonConvert` is a method in the popular third-party [Newtonsoft.Json](https://www.newtonsoft.com/json) library.</span></span>
* <span data-ttu-id="45ab9-208">Un serializador como `BinaryFormatter` se usa para deserializar una `DataSet` `DataTable` instancia de o a partir de una secuencia de bytes sin formato.</span><span class="sxs-lookup"><span data-stu-id="45ab9-208">A serializer such as `BinaryFormatter` is used to deserialize a `DataSet` or `DataTable` instance from a raw byte stream.</span></span>

<span data-ttu-id="45ab9-209">En este documento se describen las consideraciones de seguridad para los escenarios anteriores.</span><span class="sxs-lookup"><span data-stu-id="45ab9-209">This document discusses safety considerations for the preceding scenarios.</span></span>

## <a name="use-dataadapterfill-to-populate-a-dataset-from-an-untrusted-data-source"></a><span data-ttu-id="45ab9-210">Usar `DataAdapter.Fill` para rellenar a `DataSet` partir de un origen de datos que no es de confianza</span><span class="sxs-lookup"><span data-stu-id="45ab9-210">Use `DataAdapter.Fill` to populate a `DataSet` from an untrusted data source</span></span>

<span data-ttu-id="45ab9-211">`DataSet`Se puede rellenar una instancia de `DataAdapter` mediante [el `DataAdapter.Fill` método](/dotnet/api/system.data.common.dataadapter.fill), tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="45ab9-211">A `DataSet` instance can be populated from a `DataAdapter` by using [the `DataAdapter.Fill` method](/dotnet/api/system.data.common.dataadapter.fill), as shown in the following example.</span></span>

```csharp
// Assumes that connection is a valid SqlConnection object.
string queryString =
  "SELECT CustomerID, CompanyName FROM dbo.Customers";
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);

DataSet customers = new DataSet();
adapter.Fill(customers, "Customers");
```

<span data-ttu-id="45ab9-212">(El ejemplo de código anterior forma parte de un ejemplo más grande que se encuentra en [rellenar un conjunto de elementos a partir de un DataAdapter](../populating-a-dataset-from-a-dataadapter.md)).</span><span class="sxs-lookup"><span data-stu-id="45ab9-212">(The code sample above is part of a larger sample found at [Populating a DataSet from a DataAdapter](../populating-a-dataset-from-a-dataadapter.md).)</span></span>

> <span data-ttu-id="45ab9-213">La mayoría de las aplicaciones pueden simplificar y suponer que su nivel de base de datos es de confianza.</span><span class="sxs-lookup"><span data-stu-id="45ab9-213">Most apps can simplify and assume that their database layer is trusted.</span></span> <span data-ttu-id="45ab9-214">Sin embargo, si es el hábito del [modelado de amenazas](https://www.microsoft.com/securityengineering/sdl/threatmodeling) de las aplicaciones, puede considerar que el modelo de amenazas es un límite de confianza entre la aplicación (cliente) y el nivel de base de datos (servidor).</span><span class="sxs-lookup"><span data-stu-id="45ab9-214">However, if you are in the habit of [threat modeling](https://www.microsoft.com/securityengineering/sdl/threatmodeling) your apps, your threat model may consider there to be a trust boundary between the application (client) and database layer (server).</span></span> <span data-ttu-id="45ab9-215">El uso de la [autenticación mutua](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) o la [autenticación de AAD](/azure/azure-sql/database/authentication-aad-overview) entre el cliente y el servidor es una manera de ayudar a abordar los riesgos asociados a este.</span><span class="sxs-lookup"><span data-stu-id="45ab9-215">Using [mutual authentication](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) or [AAD authentication](/azure/azure-sql/database/authentication-aad-overview) between client and server is one way to help address the risks associated with this.</span></span> <span data-ttu-id="45ab9-216">En el resto de esta sección se describe el posible resultado de que un cliente se conecte a un servidor que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="45ab9-216">The remainder of this section discusses the possible result of a client connecting to an untrusted server.</span></span>

<span data-ttu-id="45ab9-217">Las consecuencias de señalar un `DataAdapter` en un origen de datos que no es de confianza dependen de la implementación del `DataAdapter` propio.</span><span class="sxs-lookup"><span data-stu-id="45ab9-217">The consequences of pointing a `DataAdapter` at an untrusted data source depend on the implementation of the `DataAdapter` itself.</span></span>

### <a name="sqldataadapter"></a><span data-ttu-id="45ab9-218">SqlDataAdapter</span><span class="sxs-lookup"><span data-stu-id="45ab9-218">SqlDataAdapter</span></span>

<span data-ttu-id="45ab9-219">En el caso del tipo integrado [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter), la referencia a un origen de datos que no es de confianza podría producir un ataque de denegación de servicio (dos).</span><span class="sxs-lookup"><span data-stu-id="45ab9-219">For the built-in type [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter), referencing an untrusted data source could result in a denial of service (DoS) attack.</span></span> <span data-ttu-id="45ab9-220">El ataque de DoS puede dar lugar a que la aplicación deje de responder o se bloquee.</span><span class="sxs-lookup"><span data-stu-id="45ab9-220">The DoS attack could result in the app becoming unresponsive or crashing.</span></span> <span data-ttu-id="45ab9-221">Si un atacante puede plantar un archivo DLL junto con la aplicación, es posible que también pueda lograr la ejecución de código local.</span><span class="sxs-lookup"><span data-stu-id="45ab9-221">If an attacker can plant a DLL alongside the app, they may also be able to achieve local code execution.</span></span>

### <a name="other-dataadapter-types"></a><span data-ttu-id="45ab9-222">Otros tipos DataAdapter</span><span class="sxs-lookup"><span data-stu-id="45ab9-222">Other DataAdapter types</span></span>

<span data-ttu-id="45ab9-223">`DataAdapter`Las implementaciones de terceros deben realizar sus propias evaluaciones sobre qué garantías de seguridad proporcionan en caso de que se produzcan entradas que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="45ab9-223">Third-party `DataAdapter` implementations must make their own assessments about what security guarantees they provide in the face of untrusted inputs.</span></span> <span data-ttu-id="45ab9-224">.NET no puede garantizar ninguna garantía de seguridad con respecto a estas implementaciones.</span><span class="sxs-lookup"><span data-stu-id="45ab9-224">.NET cannot make any safety guarantees regarding these implementations.</span></span>

<a name="dsrdtr"></a>

## <a name="datasetreadxml-and-datatablereadxml"></a><span data-ttu-id="45ab9-225">DataSet. ReadXml y DataTable. ReadXml</span><span class="sxs-lookup"><span data-stu-id="45ab9-225">DataSet.ReadXml and DataTable.ReadXml</span></span>

<span data-ttu-id="45ab9-226">Los `DataSet.ReadXml` `DataTable.ReadXml` métodos y no son seguros cuando se usan con una entrada que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="45ab9-226">The `DataSet.ReadXml` and `DataTable.ReadXml` methods are not safe when used with untrusted input.</span></span> <span data-ttu-id="45ab9-227">Se recomienda encarecidamente que los consumidores consideren el uso de una de las alternativas que se describen más adelante en este documento.</span><span class="sxs-lookup"><span data-stu-id="45ab9-227">We strongly recommend that consumers instead consider using one of the alternatives outlined later in this document.</span></span>

<span data-ttu-id="45ab9-228">Las implementaciones de `DataSet.ReadXml` y `DataTable.ReadXml` se crearon originalmente antes de que las vulnerabilidades de serialización fueran una categoría de amenazas bien entendida.</span><span class="sxs-lookup"><span data-stu-id="45ab9-228">The implementations of `DataSet.ReadXml` and `DataTable.ReadXml` were originally created before serialization vulnerabilities were a well-understood threat category.</span></span> <span data-ttu-id="45ab9-229">Como resultado, el código no sigue los procedimientos recomendados de seguridad actuales.</span><span class="sxs-lookup"><span data-stu-id="45ab9-229">As a result, the code does not follow current security best practices.</span></span> <span data-ttu-id="45ab9-230">Estas API se pueden usar como vectores para que los atacantes realicen ataques de DoS en aplicaciones Web.</span><span class="sxs-lookup"><span data-stu-id="45ab9-230">These APIs can be used as vectors for attackers to perform DoS attacks against web apps.</span></span> <span data-ttu-id="45ab9-231">Estos ataques pueden provocar que el servicio Web deje de responder o que se produzca una terminación inesperada del proceso.</span><span class="sxs-lookup"><span data-stu-id="45ab9-231">These attacks might render the web service unresponsive or result in unexpected process termination.</span></span> <span data-ttu-id="45ab9-232">El marco de trabajo no proporciona mitigaciones para estas categorías de ataque y .NET considera este comportamiento "por diseño".</span><span class="sxs-lookup"><span data-stu-id="45ab9-232">The framework does not provide mitigations for these attack categories and .NET considers this behavior "by design".</span></span>

<span data-ttu-id="45ab9-233">.NET ha publicado actualizaciones de seguridad para mitigar algunos problemas, como la divulgación de información o la ejecución remota de código en `DataSet.ReadXml` y `DataTable.ReadXml` .</span><span class="sxs-lookup"><span data-stu-id="45ab9-233">.NET has released security updates to mitigate some issues such as information disclosure or remote code execution in `DataSet.ReadXml` and `DataTable.ReadXml`.</span></span> <span data-ttu-id="45ab9-234">Es posible que las actualizaciones de seguridad de .NET no proporcionen protección completa contra estas categorías de amenaza.</span><span class="sxs-lookup"><span data-stu-id="45ab9-234">The .NET security updates may not provide complete protection against these threat categories.</span></span> <span data-ttu-id="45ab9-235">Los consumidores deben evaluar sus escenarios individuales y considerar su posible exposición a estos riesgos.</span><span class="sxs-lookup"><span data-stu-id="45ab9-235">Consumers should assess their individual scenarios and consider their potential exposure to these risks.</span></span>

<span data-ttu-id="45ab9-236">Los consumidores deben tener en cuenta que las actualizaciones de seguridad de estas API pueden afectar a la compatibilidad de aplicaciones en algunas situaciones.</span><span class="sxs-lookup"><span data-stu-id="45ab9-236">Consumers should be aware that security updates to these APIs may impact application compatibility in some situations.</span></span> <span data-ttu-id="45ab9-237">Además, existe la posibilidad de que se detecte una vulnerabilidad novedosa en estas API para la que .NET no puede publicar prácticamente una actualización de seguridad.</span><span class="sxs-lookup"><span data-stu-id="45ab9-237">Furthermore, the possibility exists that a novel vulnerability in these APIs will be discovered for which .NET can't practically publish a security update.</span></span>

<span data-ttu-id="45ab9-238">Se recomienda que los consumidores de estas API:</span><span class="sxs-lookup"><span data-stu-id="45ab9-238">We recommend that consumers of these APIs either:</span></span>

* <span data-ttu-id="45ab9-239">Considere la posibilidad de usar una de las alternativas que se describen más adelante en este documento.</span><span class="sxs-lookup"><span data-stu-id="45ab9-239">Consider using one of the alternatives outlined later in this document.</span></span>
* <span data-ttu-id="45ab9-240">Realizar evaluaciones de riesgos individuales en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="45ab9-240">Perform individual risk assessments on their apps.</span></span>

<span data-ttu-id="45ab9-241">Es responsabilidad exclusiva del consumidor determinar si se deben utilizar estas API.</span><span class="sxs-lookup"><span data-stu-id="45ab9-241">It is the consumer's sole responsibility to determine whether to utilize these APIs.</span></span> <span data-ttu-id="45ab9-242">Los consumidores deben evaluar los riesgos de seguridad, técnicos y legales, incluidos los requisitos normativos, que pueden acompañar al uso de estas API.</span><span class="sxs-lookup"><span data-stu-id="45ab9-242">Consumers should assess any security, technical, and legal risks, including regulatory requirements, that may accompany using these APIs.</span></span>

## <a name="dataset-and-datatable-via-aspnet-web-services-or-wcf"></a><span data-ttu-id="45ab9-243">DataSet y DataTable a través de los servicios Web de ASP.NET o WCF</span><span class="sxs-lookup"><span data-stu-id="45ab9-243">DataSet and DataTable via ASP.NET web services or WCF</span></span>

<span data-ttu-id="45ab9-244">Es posible aceptar una `DataSet` `DataTable` instancia de o en un servicio Web ASP.net (SOAP), como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ab9-244">It is possible to accept a `DataSet` or a `DataTable` instance in an ASP.NET (SOAP) web service, as demonstrated in the following code:</span></span>

```csharp
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(DataTable dataTable)
    {
        /* Web method implementation. */
    }
}
```

<span data-ttu-id="45ab9-245">Una variación de esto no es aceptar `DataSet` o `DataTable` directamente como parámetro, sino que se puede aceptar como parte del gráfico de objetos serializado SOAP general, tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ab9-245">A variation on this is not to accept `DataSet` or `DataTable` directly as a parameter, but instead to accept it as part of the overall SOAP serialized object graph, as shown in the following code:</span></span>

```csharp
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(MyClass data)
    {
        /* Web method implementation. */
    }
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="45ab9-246">O bien, mediante WCF en lugar de los servicios Web de ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="45ab9-246">Or, using WCF instead of ASP.NET web services:</span></span>

```csharp
using System.Data;
using System.ServiceModel;

[ServiceContract(Namespace = "http://contoso.com/")]
public interface IMyContract
{
    [OperationContract]
    string MyMethod(DataTable dataTable);
    [OperationContract]
    string MyOtherMethod(MyClass data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="45ab9-247">En todos estos casos, el modelo de amenazas y las garantías de seguridad son los mismos que los de la [sección DataSet. ReadXml y DataTable. ReadXml](#dsrdtr).</span><span class="sxs-lookup"><span data-stu-id="45ab9-247">In all of these cases, the threat model and security guarantees are the same as the [DataSet.ReadXml and DataTable.ReadXml section](#dsrdtr).</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-xmlserializer"></a><span data-ttu-id="45ab9-248">Deserialización de un conjunto de DataSet o DataTable a través de XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="45ab9-248">Deserialize a DataSet or DataTable via XmlSerializer</span></span>

<span data-ttu-id="45ab9-249">Los desarrolladores pueden usar `XmlSerializer` para deserializar `DataSet` `DataTable` las instancias de y, tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ab9-249">Developers can use `XmlSerializer` to deserialize `DataSet` and `DataTable` instances, as shown in the following code:</span></span>

```csharp
using System.Data;
using System.IO;
using System.Xml.Serialization;

public DataSet PerformDeserialization1(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(DataSet));
    return (DataSet)serializer.Deserialize(stream);
}

public MyClass PerformDeserialization2(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(MyClass));
    return (MyClass)serializer.Deserialize(stream);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="45ab9-250">En estos casos, el modelo de amenazas y las garantías de seguridad son los mismos que los de la [sección DataSet. ReadXml y DataTable. ReadXml.](#dsrdtr)</span><span class="sxs-lookup"><span data-stu-id="45ab9-250">In these cases, the threat model and security guarantees are the same as the [DataSet.ReadXml and DataTable.ReadXml section](#dsrdtr)</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-jsonconvert"></a><span data-ttu-id="45ab9-251">Deserialización de un conjunto de DataSet o DataTable a través de JsonConvert</span><span class="sxs-lookup"><span data-stu-id="45ab9-251">Deserialize a DataSet or DataTable via JsonConvert</span></span>

<span data-ttu-id="45ab9-252">La popular biblioteca de Newtonsoft de terceros [JSON.net](https://www.newtonsoft.com/json) se puede usar para deserializar `DataSet` `DataTable` las instancias de y, tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ab9-252">The popular third-party Newtonsoft library [JSON.NET](https://www.newtonsoft.com/json) can be used to deserialize `DataSet` and `DataTable` instances, as shown in the following code:</span></span>

```csharp
using System.Data;
using Newtonsoft.Json;

public DataSet PerformDeserialization1(string json) {
    return JsonConvert.DeserializeObject<DataSet>(data);
}

public MyClass PerformDeserialization2(string json) {
    return JsonConvert.DeserializeObject<MyClass>(data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="45ab9-253">La deserialización de un `DataSet` `DataTable` objeto o de este modo desde un BLOB JSON que no es de confianza no es segura.</span><span class="sxs-lookup"><span data-stu-id="45ab9-253">Deserializing a `DataSet` or `DataTable` in this manner from an untrusted JSON blob is not safe.</span></span> <span data-ttu-id="45ab9-254">Este patrón es vulnerable a ataques de denegación de servicio.</span><span class="sxs-lookup"><span data-stu-id="45ab9-254">This pattern is vulnerable to a denial of service attack.</span></span> <span data-ttu-id="45ab9-255">Este tipo de ataque podría bloquear la aplicación o representar que no responde.</span><span class="sxs-lookup"><span data-stu-id="45ab9-255">Such an attack could crash the app or render it unresponsive.</span></span>

> [!NOTE]
> <span data-ttu-id="45ab9-256">Microsoft no garantiza ni admite la implementación de bibliotecas de terceros como _Newtonsoft.Jsen_.</span><span class="sxs-lookup"><span data-stu-id="45ab9-256">Microsoft does not warrant or support the implementation of third-party libraries like _Newtonsoft.Json_.</span></span> <span data-ttu-id="45ab9-257">Esta información se proporciona para la integridad y es precisa en el momento de redactar este documento.</span><span class="sxs-lookup"><span data-stu-id="45ab9-257">This information is provided for completeness and is accurate as of the time of this writing.</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-binaryformatter"></a><span data-ttu-id="45ab9-258">Deserializar un conjunto de DataSet o DataTable a través de BinaryFormatter</span><span class="sxs-lookup"><span data-stu-id="45ab9-258">Deserialize a DataSet or DataTable via BinaryFormatter</span></span>

<span data-ttu-id="45ab9-259">Los desarrolladores nunca deben usar `BinaryFormatter` , `NetDataContractSerializer` , `SoapFormatter` o formateadores ***no seguros*** relacionados para deserializar una `DataSet` `DataTable` instancia de o de una carga que no sea de confianza:</span><span class="sxs-lookup"><span data-stu-id="45ab9-259">Developers must never use `BinaryFormatter`, `NetDataContractSerializer`, `SoapFormatter`, or related ***unsafe*** formatters to deserialize a `DataSet` or `DataTable` instance from an untrusted payload:</span></span>

* <span data-ttu-id="45ab9-260">Esto es susceptible a un ataque de ejecución de código remoto completo.</span><span class="sxs-lookup"><span data-stu-id="45ab9-260">This is susceptible to a full remote code execution attack.</span></span>
* <span data-ttu-id="45ab9-261">El uso de un personalizado `SerializationBinder` no es suficiente para evitar este tipo de ataque.</span><span class="sxs-lookup"><span data-stu-id="45ab9-261">Using a custom `SerializationBinder` is not sufficient to prevent such an attack.</span></span>

## <a name="safe-replacements"></a><span data-ttu-id="45ab9-262">Reemplazos seguros</span><span class="sxs-lookup"><span data-stu-id="45ab9-262">Safe replacements</span></span>

<span data-ttu-id="45ab9-263">En el caso de las aplicaciones que:</span><span class="sxs-lookup"><span data-stu-id="45ab9-263">For apps that either:</span></span>

* <span data-ttu-id="45ab9-264">Acepte `DataSet` o `DataTable` a través de un punto de conexión SOAP de. asmx o un extremo de WCF.</span><span class="sxs-lookup"><span data-stu-id="45ab9-264">Accept `DataSet` or `DataTable` through an .asmx SOAP endpoint or a WCF endpoint.</span></span>
* <span data-ttu-id="45ab9-265">Deserializa los datos que no son de confianza en una instancia de `DataSet` o `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="45ab9-265">Deserialize untrusted data into an instance of `DataSet` or `DataTable`.</span></span>

<span data-ttu-id="45ab9-266">Considere la posibilidad de reemplazar el modelo de objetos para utilizar [Entity Framework](/ef).</span><span class="sxs-lookup"><span data-stu-id="45ab9-266">Consider replacing the object model to use [Entity Framework](/ef).</span></span> <span data-ttu-id="45ab9-267">Entity Framework:</span><span class="sxs-lookup"><span data-stu-id="45ab9-267">Entity Framework:</span></span>

* <span data-ttu-id="45ab9-268">Es un marco de trabajo rico y moderno orientado a objetos que puede representar datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="45ab9-268">Is a rich, modern, object-oriented framework that can represent relational data.</span></span>
* <span data-ttu-id="45ab9-269">Aporta [un amplio ecosistema](/ef/core/providers/) de proveedores de bases de datos para facilitar la creación de proyectos de consultas de base de datos a través de los modelos de objetos de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="45ab9-269">Brings [a diverse ecosystem](/ef/core/providers/) of database providers to make it easy to project database queries via your Entity Framework object models.</span></span>
* <span data-ttu-id="45ab9-270">Ofrece protecciones integradas al deserializar datos de orígenes que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="45ab9-270">Offers built-in protections when deserializing data from untrusted sources.</span></span>

<span data-ttu-id="45ab9-271">En el caso de las aplicaciones que usan `.aspx` extremos SOAP, considere la posibilidad de cambiar esos puntos de conexión para usar [WCF](../../../wcf/index.md).</span><span class="sxs-lookup"><span data-stu-id="45ab9-271">For apps that use `.aspx` SOAP endpoints, consider changing those endpoints to use [WCF](../../../wcf/index.md).</span></span> <span data-ttu-id="45ab9-272">WCF es un sustituto más completo de `.asmx` servicios Web.</span><span class="sxs-lookup"><span data-stu-id="45ab9-272">WCF is a more fully featured replacement for `.asmx` web services.</span></span> <span data-ttu-id="45ab9-273">Los extremos de WCF [se pueden exponer a través de SOAP](../../../wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md) para la compatibilidad con los autores de llamadas existentes.</span><span class="sxs-lookup"><span data-stu-id="45ab9-273">WCF endpoints [can be exposed via SOAP](../../../wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md) for compatibility with existing callers.</span></span>

## <a name="code-analyzers"></a><span data-ttu-id="45ab9-274">Analizadores de código</span><span class="sxs-lookup"><span data-stu-id="45ab9-274">Code analyzers</span></span>

<span data-ttu-id="45ab9-275">Las reglas de seguridad del analizador de código, que se ejecutan cuando se compila el código fuente, pueden ayudar a encontrar vulnerabilidades relacionadas con este problema de seguridad en C# y Visual Basic código.</span><span class="sxs-lookup"><span data-stu-id="45ab9-275">Code analyzer security rules, which run when your source code is compiled, can help to find vulnerabilities related to this security issue in C# and Visual Basic code.</span></span> <span data-ttu-id="45ab9-276">Microsoft. CodeAnalysis. FxCopAnalyzers es un paquete de NuGet de analizadores de código que se distribuye en [Nuget.org](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="45ab9-276">Microsoft.CodeAnalysis.FxCopAnalyzers is a NuGet package of code analyzers that's distributed on [nuget.org](https://www.nuget.org/).</span></span>

<span data-ttu-id="45ab9-277">Para obtener información general sobre los analizadores de código, vea [información general de los analizadores de código fuente](/visualstudio/code-quality/roslyn-analyzers-overview).</span><span class="sxs-lookup"><span data-stu-id="45ab9-277">For an overview of code analyzers, see [Overview of source code analyzers](/visualstudio/code-quality/roslyn-analyzers-overview).</span></span>

<span data-ttu-id="45ab9-278">Habilite las siguientes reglas de Microsoft. CodeAnalysis. FxCopAnalyzers:</span><span class="sxs-lookup"><span data-stu-id="45ab9-278">Enable the following Microsoft.CodeAnalysis.FxCopAnalyzers rules:</span></span>

- <span data-ttu-id="45ab9-279">[CA2350](/visualstudio/code-quality/ca2350): no usar DataTable. ReadXml () con datos que no son de confianza</span><span class="sxs-lookup"><span data-stu-id="45ab9-279">[CA2350](/visualstudio/code-quality/ca2350): Do not use DataTable.ReadXml() with untrusted data</span></span>
- <span data-ttu-id="45ab9-280">[CA2351](/visualstudio/code-quality/ca2351): no usar DataSet. ReadXml () con datos que no son de confianza</span><span class="sxs-lookup"><span data-stu-id="45ab9-280">[CA2351](/visualstudio/code-quality/ca2351): Do not use DataSet.ReadXml() with untrusted data</span></span>
- <span data-ttu-id="45ab9-281">[CA2352](/visualstudio/code-quality/ca2352): un conjunto de seguridad no seguro o un DataTable en un tipo serializable pueden ser vulnerables a ataques de ejecución remota de código.</span><span class="sxs-lookup"><span data-stu-id="45ab9-281">[CA2352](/visualstudio/code-quality/ca2352): Unsafe DataSet or DataTable in serializable type can be vulnerable to remote code execution attacks</span></span>
- <span data-ttu-id="45ab9-282">[CA2353](/visualstudio/code-quality/ca2353): conjunto de seguridad no seguro o DataTable en tipo serializable</span><span class="sxs-lookup"><span data-stu-id="45ab9-282">[CA2353](/visualstudio/code-quality/ca2353): Unsafe DataSet or DataTable in serializable type</span></span>
- <span data-ttu-id="45ab9-283">[CA2354](/visualstudio/code-quality/ca2354): un conjunto de objetos no seguro o DataTable en el gráfico de objetos deserializados puede ser vulnerable a ataques de ejecución remota de código.</span><span class="sxs-lookup"><span data-stu-id="45ab9-283">[CA2354](/visualstudio/code-quality/ca2354): Unsafe DataSet or DataTable in deserialized object graph can be vulnerable to remote code execution attacks</span></span>
- <span data-ttu-id="45ab9-284">[CA2355](/visualstudio/code-quality/ca2355): el tipo de DataTable o el conjunto de texto no seguro que se encuentra en el gráfico de objetos deserializables</span><span class="sxs-lookup"><span data-stu-id="45ab9-284">[CA2355](/visualstudio/code-quality/ca2355): Unsafe DataSet or DataTable type found in deserializable object graph</span></span>
- <span data-ttu-id="45ab9-285">[CA2356](/visualstudio/code-quality/ca2356): tipo de objeto DataTable o DataSet no seguro en el gráfico de objetos deserializables Web</span><span class="sxs-lookup"><span data-stu-id="45ab9-285">[CA2356](/visualstudio/code-quality/ca2356): Unsafe DataSet or DataTable type in web deserializable object graph</span></span>
- <span data-ttu-id="45ab9-286">[CA2361](/visualstudio/code-quality/ca2361): Asegúrese de que la clase generada automáticamente que contiene DataSet. ReadXml () no se utiliza con datos que no son de confianza</span><span class="sxs-lookup"><span data-stu-id="45ab9-286">[CA2361](/visualstudio/code-quality/ca2361): Ensure autogenerated class containing DataSet.ReadXml() is not used with untrusted data</span></span>
- <span data-ttu-id="45ab9-287">[CA2362](/visualstudio/code-quality/ca2362): el conjunto de seguridad no seguro o DataTable en el tipo serializable generado automáticamente puede ser vulnerable a ataques de ejecución remota de código.</span><span class="sxs-lookup"><span data-stu-id="45ab9-287">[CA2362](/visualstudio/code-quality/ca2362): Unsafe DataSet or DataTable in autogenerated serializable type can be vulnerable to remote code execution attacks</span></span>

<span data-ttu-id="45ab9-288">Para obtener más información sobre cómo configurar las reglas, consulte [usar analizadores de código](/visualstudio/code-quality/use-roslyn-analyzers).</span><span class="sxs-lookup"><span data-stu-id="45ab9-288">For more information about configuring rules, see [Use code analyzers](/visualstudio/code-quality/use-roslyn-analyzers).</span></span>

<span data-ttu-id="45ab9-289">Las nuevas reglas de seguridad están disponibles en los siguientes paquetes NuGet:</span><span class="sxs-lookup"><span data-stu-id="45ab9-289">The new security rules are available in the following NuGet packages:</span></span>

- <span data-ttu-id="45ab9-290">Microsoft. CodeAnalysis. FxCopAnalyzers 3.3.0: para Visual Studio 2019 versión 16,3 o posterior</span><span class="sxs-lookup"><span data-stu-id="45ab9-290">Microsoft.CodeAnalysis.FxCopAnalyzers 3.3.0: for Visual Studio 2019 version 16.3 or later</span></span>
- <span data-ttu-id="45ab9-291">Microsoft. CodeAnalysis. FxCopAnalyzers 2.9.11: para Visual Studio 2017 versión 15,9 o posterior</span><span class="sxs-lookup"><span data-stu-id="45ab9-291">Microsoft.CodeAnalysis.FxCopAnalyzers 2.9.11: for Visual Studio 2017 version 15.9 or later</span></span>
