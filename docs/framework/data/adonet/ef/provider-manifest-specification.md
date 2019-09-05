---
title: Especificación del manifiesto del proveedor
ms.date: 03/30/2017
ms.assetid: bb450b47-8951-4f99-9350-26f05a4d4e46
ms.openlocfilehash: 6b924f484e6635760d08d0eba9fb9436bdd8bc88
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248589"
---
# <a name="provider-manifest-specification"></a><span data-ttu-id="05d58-102">Especificación del manifiesto del proveedor</span><span class="sxs-lookup"><span data-stu-id="05d58-102">Provider Manifest Specification</span></span>
<span data-ttu-id="05d58-103">En esta sección se explica cómo puede un proveedor de almacén de datos admitir los tipos y funciones del almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="05d58-103">This section discusses how a data store provider can support the types and functions in the data store.</span></span>  
  
 <span data-ttu-id="05d58-104">Servicios de entidad funciona con independencia de un proveedor de almacén de datos concreto aunque permite a un proveedor de datos definir explícitamente la forma en que los modelos, las asignaciones y las consultas interactuarán con un almacén de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="05d58-104">Entity Services operates independently of a specific data store provider yet still allows a data provider to explicitly define how models, mappings, and queries interact with an underlying data store.</span></span> <span data-ttu-id="05d58-105">Sin una capa de abstracción, Servicios de entidad solo podría seleccionarse como destino en un determinado almacén de datos o proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="05d58-105">Without a layer of abstraction, Entity Services could only be targeted at a specific data store or data provider.</span></span>  
  
 <span data-ttu-id="05d58-106">Los tipos que admite el proveedor están directa o indirectamente admitidos por la base de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="05d58-106">Types that the provider supports are directly or indirectly supported by the underlying database.</span></span> <span data-ttu-id="05d58-107">Estos tipos no son necesariamente los tipos de almacén exactos, sino aquellos que el proveedor utiliza para admitir [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05d58-107">These types are not necessarily the exact store types, but the types the provider uses to support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="05d58-108">Los tipos de proveedor/almacén se describen en los términos de Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="05d58-108">Provider/store types are described in the Entity Data Model (EDM) terms.</span></span>  
  
 <span data-ttu-id="05d58-109">Los tipos de parámetro y de valores devueltos para las funciones admitidas por el almacén de datos se especifican en términos de EDM.</span><span class="sxs-lookup"><span data-stu-id="05d58-109">Parameter and return types for the functions supported by the data store are specified in EDM terms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05d58-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="05d58-110">Requirements</span></span>  
 <span data-ttu-id="05d58-111">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] y el almacén de datos necesitan poder pasarse datos de uno a otro en tipos conocidos sin que se produzcan pérdidas de datos o truncamientos.</span><span class="sxs-lookup"><span data-stu-id="05d58-111">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and the data store need to be able to pass data back and forth in known types without any data loss or truncation.</span></span>  
  
 <span data-ttu-id="05d58-112">Las herramientas deben ser capaces de cargar el manifiesto del proveedor en tiempo de diseño sin tener que abrir una conexión al almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="05d58-112">The provider manifest must be loadable by tools at design time without having to open a connection to the data store.</span></span>  
  
 <span data-ttu-id="05d58-113">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Distingue mayúsculas de minúsculas, pero es posible que el almacén de datos subyacente no sea.</span><span class="sxs-lookup"><span data-stu-id="05d58-113">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is case sensitive, but the underlying data store may not be.</span></span> <span data-ttu-id="05d58-114">Cuando los artefactos de EDM (identificadores y nombres de tipo, por ejemplo) se definen y se utilizan en el manifiesto, deben utilizar la distinción entre mayúsculas y minúsculas de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05d58-114">When EDM artifacts (identifiers and type names, for example) are defined and used in the manifest, they must use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] case sensitivity.</span></span> <span data-ttu-id="05d58-115">Si en el manifiesto del proveedor aparecen elementos de almacén de datos que pueden distinguir entre mayúsculas y minúsculas, esa grafía debe mantenerse en el manifiesto del proveedor.</span><span class="sxs-lookup"><span data-stu-id="05d58-115">If data store elements that may be case sensitive appear in the provider manifest, that casing needs to be maintained in the provider manifest.</span></span>  
  
 <span data-ttu-id="05d58-116">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] requiere un manifiesto del proveedor para todos los proveedores de datos.</span><span class="sxs-lookup"><span data-stu-id="05d58-116">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] requires a provider manifest for all data providers.</span></span> <span data-ttu-id="05d58-117">Si intenta usar un proveedor que no tiene un manifiesto de proveedor con [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], obtendrá un error.</span><span class="sxs-lookup"><span data-stu-id="05d58-117">If you try to use a provider that does not have a provider manifest with the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you will get an error.</span></span>  
  
 <span data-ttu-id="05d58-118">En la siguiente tabla se describen los tipos de excepción que [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] genera cuando surgen excepciones de la interacción con los proveedores:</span><span class="sxs-lookup"><span data-stu-id="05d58-118">The following table describes the kinds of exceptions the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] would throw when exceptions arise through provider interaction:</span></span>  
  
|<span data-ttu-id="05d58-119">Problema</span><span class="sxs-lookup"><span data-stu-id="05d58-119">Issue</span></span>|<span data-ttu-id="05d58-120">Excepción</span><span class="sxs-lookup"><span data-stu-id="05d58-120">Exception</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="05d58-121">El proveedor no admite GetProviderManifest en DbProviderServices.</span><span class="sxs-lookup"><span data-stu-id="05d58-121">The Provider does not support GetProviderManifest in DbProviderServices.</span></span>|<span data-ttu-id="05d58-122">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="05d58-122">ProviderIncompatibleException</span></span>|  
|<span data-ttu-id="05d58-123">Falta el manifiesto del proveedor: el proveedor devuelve `null` cuando se intenta recuperar el manifiesto del proveedor.</span><span class="sxs-lookup"><span data-stu-id="05d58-123">Missing provider manifest: the provider returns `null` when attempting to retrieve the provider manifest.</span></span>|<span data-ttu-id="05d58-124">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="05d58-124">ProviderIncompatibleException</span></span>|  
|<span data-ttu-id="05d58-125">Manifiesto del proveedor no válido: el proveedor devuelve XML no válido cuando se intenta recuperar el manifiesto del proveedor.</span><span class="sxs-lookup"><span data-stu-id="05d58-125">Invalid provider manifest: the provider returns invalid XML when attempting to retrieve the provider manifest.</span></span>|<span data-ttu-id="05d58-126">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="05d58-126">ProviderIncompatibleException</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="05d58-127">Escenarios</span><span class="sxs-lookup"><span data-stu-id="05d58-127">Scenarios</span></span>  
 <span data-ttu-id="05d58-128">Un proveedor debe admitir los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="05d58-128">A provider should support the following scenarios:</span></span>  
  
### <a name="writing-a-provider-with-symmetric-type-mapping"></a><span data-ttu-id="05d58-129">Escribir un proveedor con asignación de tipos simétrica</span><span class="sxs-lookup"><span data-stu-id="05d58-129">Writing a Provider with Symmetric Type Mapping</span></span>  
 <span data-ttu-id="05d58-130">Puede escribir un proveedor para el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] donde cada tipo de almacén se asigna a un tipo de EDM único, independientemente de la dirección de asignación.</span><span class="sxs-lookup"><span data-stu-id="05d58-130">You can write a provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] where each store type maps to a single EDM type, regardless of the mapping direction.</span></span> <span data-ttu-id="05d58-131">En el caso de un tipo de proveedor que tenga una asignación simple que se corresponda con un tipo de EDM, puede utilizar una solución simétrica, porque el sistema de tipos es simple o coincide con los tipos de EDM.</span><span class="sxs-lookup"><span data-stu-id="05d58-131">For a provider type that has very simple mapping that corresponds with an EDM type, you can use a symmetric solution because the type system is simple or matches EDM types.</span></span>  
  
 <span data-ttu-id="05d58-132">Puede utilizar la simplicidad de su dominio y generar un manifiesto del proveedor declarativo estático.</span><span class="sxs-lookup"><span data-stu-id="05d58-132">You can use the simplicity of their domain and produce a static declarative provider manifest.</span></span>  
  
 <span data-ttu-id="05d58-133">Puede escribir un archivo XML que tenga dos secciones:</span><span class="sxs-lookup"><span data-stu-id="05d58-133">You write an XML file that has two sections:</span></span>  
  
- <span data-ttu-id="05d58-134">Una lista de tipos de proveedor expresada en términos de "equivalente de EDM" de un tipo de almacén o función.</span><span class="sxs-lookup"><span data-stu-id="05d58-134">A list of provider types expressed in terms of the "EDM counterpart" of a store type or function.</span></span> <span data-ttu-id="05d58-135">Los tipos de almacén tienen tipos de EDM equivalentes.</span><span class="sxs-lookup"><span data-stu-id="05d58-135">Store types have counterpart EDM types.</span></span> <span data-ttu-id="05d58-136">Las funciones de almacén tienen funciones de EDM correspondientes.</span><span class="sxs-lookup"><span data-stu-id="05d58-136">Store functions have corresponding EDM functions.</span></span> <span data-ttu-id="05d58-137">Por ejemplo, varchar es un tipo de SQL Server, pero el tipo de EDM correspondiente es string.</span><span class="sxs-lookup"><span data-stu-id="05d58-137">For example, varchar is a SQL Server type but the corresponding EDM type is string.</span></span>  
  
- <span data-ttu-id="05d58-138">Una lista de funciones admitida por el proveedor donde los tipos de parámetro y de valores devueltos se expresen en términos de EDM.</span><span class="sxs-lookup"><span data-stu-id="05d58-138">A list of functions supported by the provider where parameter and return types are expressed in EDM terms.</span></span>  
  
### <a name="writing-a-provider-with-asymmetric-type-mapping"></a><span data-ttu-id="05d58-139">Escribir un proveedor con asignación de tipos asimétrica</span><span class="sxs-lookup"><span data-stu-id="05d58-139">Writing a Provider with Asymmetric Type Mapping</span></span>  
 <span data-ttu-id="05d58-140">Cuando se escribe un proveedor de almacén de datos para [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], la asignación de tipos de EDM a proveedor para algunos tipos puede diferir de la asignación de tipos de proveedor a EDM.</span><span class="sxs-lookup"><span data-stu-id="05d58-140">When writing a data store provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], the EDM-to-provider type mapping for some types may be different from provider-to-EDM type mapping.</span></span> <span data-ttu-id="05d58-141">Por ejemplo, la cadena PrimitiveTypeKind.String de EDM ilimitada se puede asignar a nvarchar(4000) en el proveedor, mientras que nvarchar(4000) se asigna a la cadena PrimitiveTypeKind.String(MaxLength=4000) de EDM.</span><span class="sxs-lookup"><span data-stu-id="05d58-141">For instance, unbounded EDM PrimitiveTypeKind.String may map to nvarchar(4000) on the provider, while nvarchar(4000) maps to the EDM PrimitiveTypeKind.String(MaxLength=4000).</span></span>  
  
 <span data-ttu-id="05d58-142">Puede escribir un archivo XML que tenga dos secciones:</span><span class="sxs-lookup"><span data-stu-id="05d58-142">You write an XML file that has two sections:</span></span>  
  
- <span data-ttu-id="05d58-143">Una lista de tipos de proveedor expresada en términos de EDM y definir la asignación para ambas direcciones: De EDM a proveedor y de proveedor a EDM.</span><span class="sxs-lookup"><span data-stu-id="05d58-143">A list of provider types expressed in EDM terms and define mapping for both direction: EDM-to-provider and provider-to-EDM.</span></span>  
  
- <span data-ttu-id="05d58-144">Una lista de funciones admitida por el proveedor donde los tipos de parámetro y de valores devueltos se expresen en términos de EDM.</span><span class="sxs-lookup"><span data-stu-id="05d58-144">A list of functions supported by the provider where parameter and return types are expressed in EDM terms.</span></span>  
  
## <a name="provider-manifest-discoverability"></a><span data-ttu-id="05d58-145">Detectabilidad del manifiesto del proveedor</span><span class="sxs-lookup"><span data-stu-id="05d58-145">Provider Manifest Discoverability</span></span>  
 <span data-ttu-id="05d58-146">Varios tipos de componente utilizan indirectamente el manifiesto en Servicios de entidad (por ejemplo Tools o Query), pero los metadatos lo aprovechan de forma más directa con el uso del cargador de metadatos del almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="05d58-146">The manifest is used indirectly by several component types in Entity Services (for example Tools or Query) but more directly leveraged by metadata through the use of the data store metadata loader.</span></span>  
  
 <span data-ttu-id="05d58-147">![dfb3d02b&#45;7a8c&#45;4d51&#45;ac5a&#45;a73d8aa145e6](./media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")</span><span class="sxs-lookup"><span data-stu-id="05d58-147">![dfb3d02b&#45;7a8c&#45;4d51&#45;ac5a&#45;a73d8aa145e6](./media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")</span></span>  
  
 <span data-ttu-id="05d58-148">Sin embargo, un proveedor determinado puede admitir almacenes diferentes o distintas versiones del mismo almacén.</span><span class="sxs-lookup"><span data-stu-id="05d58-148">However, a given provider may support different stores or different versions of the same store.</span></span> <span data-ttu-id="05d58-149">Por consiguiente, un proveedor debe notificar un manifiesto distinto para cada almacén de datos compatible.</span><span class="sxs-lookup"><span data-stu-id="05d58-149">Therefore, a provider must report a different manifest for each supported data store.</span></span>  
  
### <a name="provider-manifest-token"></a><span data-ttu-id="05d58-150">Token del manifiesto del proveedor</span><span class="sxs-lookup"><span data-stu-id="05d58-150">Provider Manifest Token</span></span>  
 <span data-ttu-id="05d58-151">Cuando se abre una conexión al almacén de datos, el proveedor puede consultar información para devolver el manifiesto correcto.</span><span class="sxs-lookup"><span data-stu-id="05d58-151">When a data store connection is opened, the provider can query for information to return the right manifest.</span></span> <span data-ttu-id="05d58-152">Esto puede no ser posible en escenarios sin conexión en los que no haya información de conexión disponible o cuando no se pueda conectar con el almacén.</span><span class="sxs-lookup"><span data-stu-id="05d58-152">This may not be possible in offline scenarios where connection information is not available or when it is not possible to connect to the store.</span></span> <span data-ttu-id="05d58-153">Identifique el manifiesto mediante el atributo `ProviderManifestToken` del elemento `Schema` en el archivo .ssdl.</span><span class="sxs-lookup"><span data-stu-id="05d58-153">Identify the manifest by using the `ProviderManifestToken` attribute of the `Schema` element in the .ssdl file.</span></span> <span data-ttu-id="05d58-154">No hay ningún formato obligatorio para este atributo; el proveedor elige la información mínima necesaria para identificar un manifiesto sin abrir una conexión al almacén.</span><span class="sxs-lookup"><span data-stu-id="05d58-154">There is no required format for this attribute; the provider chooses the minimum information needed to identify a manifest without opening a connection to the store.</span></span>  
  
 <span data-ttu-id="05d58-155">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="05d58-155">For example:</span></span>  
  
```xml  
<Schema Namespace="Northwind" Provider="System.Data.SqlClient" ProviderManifestToken="2005" xmlns:edm="http://schemas.microsoft.com/ado/2006/04/edm/ssdl" xmlns="http://schemas.microsoft.com/ado/2006/04/edm/ssdl">  
```  
  
## <a name="provider-manifest-programming-model"></a><span data-ttu-id="05d58-156">Modelo de programación del manifiesto del proveedor</span><span class="sxs-lookup"><span data-stu-id="05d58-156">Provider Manifest Programming Model</span></span>  
 <span data-ttu-id="05d58-157">Los proveedores se derivan de <xref:System.Data.Common.DbXmlEnabledProviderManifest>, lo que les permite especificar sus manifiestos mediante declaración.</span><span class="sxs-lookup"><span data-stu-id="05d58-157">Providers derive from <xref:System.Data.Common.DbXmlEnabledProviderManifest>, which allows them to specify their manifests declaratively.</span></span> <span data-ttu-id="05d58-158">La siguiente ilustración muestra la jerarquía de clases de un proveedor:</span><span class="sxs-lookup"><span data-stu-id="05d58-158">The following illustration shows the class hierarchy of a provider:</span></span>  
  
 <span data-ttu-id="05d58-159">![None](./media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")</span><span class="sxs-lookup"><span data-stu-id="05d58-159">![None](./media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")</span></span>  
  
### <a name="discoverability-api"></a><span data-ttu-id="05d58-160">API de detectabilidad</span><span class="sxs-lookup"><span data-stu-id="05d58-160">Discoverability API</span></span>  
 <span data-ttu-id="05d58-161">El cargador Metadatos de almacenamiento (StoreItemCollection) carga el manifiesto de proveedor, bien mediante una conexión al almacén de datos o utilizando un token de manifiesto del proveedor.</span><span class="sxs-lookup"><span data-stu-id="05d58-161">The provider manifest is loaded by the Store Metadata loader (StoreItemCollection), either by using a data store connection or a provider manifest token.</span></span>  
  
#### <a name="using-a-data-store-connection"></a><span data-ttu-id="05d58-162">Utilizar una conexión al almacén de datos</span><span class="sxs-lookup"><span data-stu-id="05d58-162">Using a Data Store Connection</span></span>  
 <span data-ttu-id="05d58-163">Cuando la conexión del almacén de datos está disponible <xref:System.Data.Common.DbProviderServices.GetProviderManifestToken%2A?displayProperty=nameWithType> , llame a para devolver el token que se <xref:System.Data.Common.DbProviderServices.GetProviderManifest%2A> pasa al método, <xref:System.Data.Common.DbProviderManifest>que devuelve.</span><span class="sxs-lookup"><span data-stu-id="05d58-163">When the data store connection is available, call <xref:System.Data.Common.DbProviderServices.GetProviderManifestToken%2A?displayProperty=nameWithType> to return the token that is passed to the <xref:System.Data.Common.DbProviderServices.GetProviderManifest%2A> method, which returns <xref:System.Data.Common.DbProviderManifest>.</span></span> <span data-ttu-id="05d58-164">Este método delega en la implementación del proveedor de `GetDbProviderManifestToken`.</span><span class="sxs-lookup"><span data-stu-id="05d58-164">This method delegates to the provider's implementation of `GetDbProviderManifestToken`.</span></span>  
  
```csharp
public string GetProviderManifestToken(DbConnection connection);  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
#### <a name="using-a-provider-manifest-token"></a><span data-ttu-id="05d58-165">Usar un token de manifiesto del proveedor</span><span class="sxs-lookup"><span data-stu-id="05d58-165">Using a Provider Manifest Token</span></span>  
 <span data-ttu-id="05d58-166">En el caso del escenario sin conexión, el token se toma de la representación SSDL.</span><span class="sxs-lookup"><span data-stu-id="05d58-166">For the offline scenario, the token is picked from SSDL representation.</span></span> <span data-ttu-id="05d58-167">El SSDL le permite especificar un ProviderManifestToken (vea el [elemento Schema (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="05d58-167">The SSDL allows you to specify a ProviderManifestToken (see [Schema Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl) for more information).</span></span> <span data-ttu-id="05d58-168">Por ejemplo, si no se puede abrir una conexión, SSDL tiene un token de manifiesto del proveedor que especifica información sobre el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="05d58-168">For example, if a connection cannot be opened, the SSDL has a provider manifest token that specifies information about the manifest.</span></span>  
  
```  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
### <a name="provider-manifest-schema"></a><span data-ttu-id="05d58-169">Esquema del manifiesto del proveedor</span><span class="sxs-lookup"><span data-stu-id="05d58-169">Provider Manifest Schema</span></span>  
 <span data-ttu-id="05d58-170">El esquema de información definido para cada proveedor contiene la información estática que van a utilizar los metadatos:</span><span class="sxs-lookup"><span data-stu-id="05d58-170">The schema of information defined for each provider contains the static information to be consumed by metadata:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema elementFormDefault="qualified"  
   xmlns:xs="http://www.w3.org/2001/XMLSchema"  
   targetNamespace="http://schemas.microsoft.com/ado/2006/04/edm/providermanifest"  
   xmlns:pm="http://schemas.microsoft.com/ado/2006/04/edm/providermanifest">  
  
  <xs:element name="ProviderManifest">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="Types" type="pm:TTypes" minOccurs="1" maxOccurs="1" />  
        <xs:element name="Functions" type="pm:TFunctions" minOccurs="0" maxOccurs="1"/>  
      </xs:sequence>  
      <xs:attribute name="Namespace" type="xs:string" use="required"/>  
    </xs:complexType>  
  </xs:element>  
  <xs:complexType name="TVersion">  
    <xs:attribute name="Major" type="xs:int" use="required" />  
    <xs:attribute name="Minor" type="xs:int" use="required" />  
    <xs:attribute name="Build" type="xs:int" use="required" />  
    <xs:attribute name="Revision" type="xs:int" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TIntegerFacetDescription">  
    <xs:attribute name="Minimum" type="xs:int" use="optional" />  
    <xs:attribute name="Maximum" type="xs:int" use="optional" />  
    <xs:attribute name="DefaultValue" type="xs:int" use="optional" />  
    <xs:attribute name="Constant" type="xs:boolean" default="false" />  
  </xs:complexType>  
  
  <xs:complexType name="TBooleanFacetDescription">  
    <xs:attribute name="DefaultValue" type="xs:boolean" use="optional" />  
    <xs:attribute name="Constant" type="xs:boolean" default="true" />  
  </xs:complexType>  
  
  <xs:complexType name="TDateTimeFacetDescription">  
    <xs:attribute name="Constant" type="xs:boolean" default="false" />  
  </xs:complexType>  
  
  <xs:complexType name="TFacetDescriptions">  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="Precision" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="Scale" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="MaxLength" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="Unicode" minOccurs="0" maxOccurs="1" type="pm:TBooleanFacetDescription"/>  
      <xs:element name="FixedLength" minOccurs="0" maxOccurs="1" type="pm:TBooleanFacetDescription"/>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:complexType name="TType">  
    <xs:sequence>  
      <xs:element name="FacetDescriptions" type="pm:TFacetDescriptions" minOccurs="0" maxOccurs="1"/>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required"/>  
    <xs:attribute name="PrimitiveTypeKind" type="pm:TPrimitiveTypeKind" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TTypes">  
    <xs:sequence>  
      <xs:element name="Type" type="pm:TType" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:sequence>  
  </xs:complexType>  
  
  <xs:attributeGroup name="TFacetAttribute">  
    <xs:attribute name="Precision" type="xs:int" use="optional"/>  
    <xs:attribute name="Scale" type="xs:int" use="optional"/>  
    <xs:attribute name="MaxLength" type="xs:int" use="optional"/>  
    <xs:attribute name="Unicode" type="xs:boolean" use="optional"/>  
    <xs:attribute name="FixedLength" type="xs:boolean" use="optional"/>  
  </xs:attributeGroup>  
  
  <xs:complexType name="TFunctionParameter">  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attributeGroup ref="pm:TFacetAttribute" />  
    <xs:attribute name="Mode" type="pm:TParameterDirection" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TReturnType">  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attributeGroup ref="pm:TFacetAttribute" />  
  </xs:complexType>  
  
  <xs:complexType name="TFunction">  
    <xs:choice minOccurs="0" maxOccurs ="unbounded">  
      <xs:element name ="ReturnType" type="pm:TReturnType" minOccurs="0" maxOccurs="1" />  
      <xs:element name="Parameter" type="pm:TFunctionParameter" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:choice>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Aggregate" type="xs:boolean" use="optional" />  
    <xs:attribute name="BuiltIn" type="xs:boolean" use="optional" />  
    <xs:attribute name="StoreFunctionName" type="xs:string" use="optional" />  
    <xs:attribute name="NiladicFunction" type="xs:boolean" use="optional" />  
    <xs:attribute name="ParameterTypeSemantics" type="pm:TParameterTypeSemantics" use="optional" default="AllowImplicitConversion" />  
  </xs:complexType>  
  
  <xs:complexType name="TFunctions">  
    <xs:sequence>  
      <xs:element name="Function" type="pm:TFunction" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:sequence>  
  </xs:complexType>  
  
  <xs:simpleType name="TPrimitiveTypeKind">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Binary"/>  
      <xs:enumeration value="Boolean"/>  
      <xs:enumeration value="Byte"/>  
      <xs:enumeration value="Decimal"/>  
      <xs:enumeration value="DateTime"/>  
      <xs:enumeration value="Time"/>  
      <xs:enumeration value="DateTimeOffset"/>          
      <xs:enumeration value="Double"/>  
      <xs:enumeration value="Guid"/>  
      <xs:enumeration value="Single"/>  
      <xs:enumeration value="SByte"/>  
      <xs:enumeration value="Int16"/>  
      <xs:enumeration value="Int32"/>  
      <xs:enumeration value="Int64"/>  
      <xs:enumeration value="String"/>  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:simpleType name="TParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In"/>  
      <xs:enumeration value="Out"/>  
      <xs:enumeration value="InOut"/>  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:simpleType name="TParameterTypeSemantics">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="ExactMatchOnly" />  
      <xs:enumeration value="AllowImplicitPromotion" />  
      <xs:enumeration value="AllowImplicitConversion" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
#### <a name="types-node"></a><span data-ttu-id="05d58-171">Nodo Types</span><span class="sxs-lookup"><span data-stu-id="05d58-171">Types Node</span></span>  
 <span data-ttu-id="05d58-172">El nodo Types del manifiesto del proveedor contiene información sobre los tipos admitidos de forma nativa por el almacén de datos o a través del proveedor.</span><span class="sxs-lookup"><span data-stu-id="05d58-172">The Types node in the provider manifest contains information about the Types that are supported natively by the data store or through the provider.</span></span>  
  
##### <a name="type-node"></a><span data-ttu-id="05d58-173">Nodo Type</span><span class="sxs-lookup"><span data-stu-id="05d58-173">Type Node</span></span>  
 <span data-ttu-id="05d58-174">Cada nodo Type define un tipo de proveedor en términos de EDM.</span><span class="sxs-lookup"><span data-stu-id="05d58-174">Each Type node defines a provider type in terms of EDM.</span></span> <span data-ttu-id="05d58-175">El nodo Type describe el nombre del tipo de proveedor e información relacionada con el tipo de modelo al que está asignado, así como facetas que describen esa asignación de tipos.</span><span class="sxs-lookup"><span data-stu-id="05d58-175">The Type node describes the name of the provider type, and information related to the model type it maps to and facets to describe that type mapping.</span></span>  
  
 <span data-ttu-id="05d58-176">Para expresar esta información de tipos en el manifiesto del proveedor, cada declaración de TypeInformation debe definir distintas descripciones de facetas para cada Type:</span><span class="sxs-lookup"><span data-stu-id="05d58-176">In order to express this type information in the provider manifest, each TypeInformation declaration must define several facet descriptions for each Type:</span></span>  
  
|<span data-ttu-id="05d58-177">Nombre de atributo</span><span class="sxs-lookup"><span data-stu-id="05d58-177">Attribute Name</span></span>|<span data-ttu-id="05d58-178">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="05d58-178">Data Type</span></span>|<span data-ttu-id="05d58-179">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="05d58-179">Required</span></span>|<span data-ttu-id="05d58-180">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="05d58-180">Default Value</span></span>|<span data-ttu-id="05d58-181">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="05d58-181">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="05d58-182">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="05d58-182">Name</span></span>|<span data-ttu-id="05d58-183">string</span><span class="sxs-lookup"><span data-stu-id="05d58-183">String</span></span>|<span data-ttu-id="05d58-184">Sí</span><span class="sxs-lookup"><span data-stu-id="05d58-184">Yes</span></span>|<span data-ttu-id="05d58-185">N/D</span><span class="sxs-lookup"><span data-stu-id="05d58-185">n/a</span></span>|<span data-ttu-id="05d58-186">El nombre del tipo de datos específico del proveedor</span><span class="sxs-lookup"><span data-stu-id="05d58-186">Provider-specific data type name</span></span>|  
|<span data-ttu-id="05d58-187">PrimitiveTypeKind</span><span class="sxs-lookup"><span data-stu-id="05d58-187">PrimitiveTypeKind</span></span>|<span data-ttu-id="05d58-188">PrimitiveTypeKind</span><span class="sxs-lookup"><span data-stu-id="05d58-188">PrimitiveTypeKind</span></span>|<span data-ttu-id="05d58-189">Sí</span><span class="sxs-lookup"><span data-stu-id="05d58-189">Yes</span></span>|<span data-ttu-id="05d58-190">N/D</span><span class="sxs-lookup"><span data-stu-id="05d58-190">n/a</span></span>|<span data-ttu-id="05d58-191">Nombre de tipo EDM</span><span class="sxs-lookup"><span data-stu-id="05d58-191">EDM type name</span></span>|  
  
###### <a name="function-node"></a><span data-ttu-id="05d58-192">Nodo Function</span><span class="sxs-lookup"><span data-stu-id="05d58-192">Function Node</span></span>  
 <span data-ttu-id="05d58-193">Cada nodo Function define una función única disponible a través del proveedor.</span><span class="sxs-lookup"><span data-stu-id="05d58-193">Each Function defines a single function available through the provider.</span></span>  
  
|<span data-ttu-id="05d58-194">Nombre de atributo</span><span class="sxs-lookup"><span data-stu-id="05d58-194">Attribute Name</span></span>|<span data-ttu-id="05d58-195">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="05d58-195">Data Type</span></span>|<span data-ttu-id="05d58-196">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="05d58-196">Required</span></span>|<span data-ttu-id="05d58-197">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="05d58-197">Default Value</span></span>|<span data-ttu-id="05d58-198">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="05d58-198">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="05d58-199">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="05d58-199">Name</span></span>|<span data-ttu-id="05d58-200">string</span><span class="sxs-lookup"><span data-stu-id="05d58-200">String</span></span>|<span data-ttu-id="05d58-201">Sí</span><span class="sxs-lookup"><span data-stu-id="05d58-201">Yes</span></span>|<span data-ttu-id="05d58-202">N/D</span><span class="sxs-lookup"><span data-stu-id="05d58-202">n/a</span></span>|<span data-ttu-id="05d58-203">Identificador/nombre de la función</span><span class="sxs-lookup"><span data-stu-id="05d58-203">Identifier/name of the function</span></span>|  
|<span data-ttu-id="05d58-204">ReturnType</span><span class="sxs-lookup"><span data-stu-id="05d58-204">ReturnType</span></span>|<span data-ttu-id="05d58-205">string</span><span class="sxs-lookup"><span data-stu-id="05d58-205">String</span></span>|<span data-ttu-id="05d58-206">Sin</span><span class="sxs-lookup"><span data-stu-id="05d58-206">No</span></span>|<span data-ttu-id="05d58-207">Void</span><span class="sxs-lookup"><span data-stu-id="05d58-207">Void</span></span>|<span data-ttu-id="05d58-208">El tipo de valor devuelto EDM de la función</span><span class="sxs-lookup"><span data-stu-id="05d58-208">The EDM return type of the function</span></span>|  
|<span data-ttu-id="05d58-209">Agregar</span><span class="sxs-lookup"><span data-stu-id="05d58-209">Aggregate</span></span>|<span data-ttu-id="05d58-210">Boolean</span><span class="sxs-lookup"><span data-stu-id="05d58-210">Boolean</span></span>|<span data-ttu-id="05d58-211">Sin</span><span class="sxs-lookup"><span data-stu-id="05d58-211">No</span></span>|<span data-ttu-id="05d58-212">False</span><span class="sxs-lookup"><span data-stu-id="05d58-212">False</span></span>|<span data-ttu-id="05d58-213">True si la función es una función de agregado</span><span class="sxs-lookup"><span data-stu-id="05d58-213">True if the function is an aggregate function</span></span>|  
|<span data-ttu-id="05d58-214">BuiltIn</span><span class="sxs-lookup"><span data-stu-id="05d58-214">BuiltIn</span></span>|<span data-ttu-id="05d58-215">Boolean</span><span class="sxs-lookup"><span data-stu-id="05d58-215">Boolean</span></span>|<span data-ttu-id="05d58-216">Sin</span><span class="sxs-lookup"><span data-stu-id="05d58-216">No</span></span>|<span data-ttu-id="05d58-217">True</span><span class="sxs-lookup"><span data-stu-id="05d58-217">True</span></span>|<span data-ttu-id="05d58-218">True si la función está integrada en el almacén de datos</span><span class="sxs-lookup"><span data-stu-id="05d58-218">True if the function is built into the data store</span></span>|  
|<span data-ttu-id="05d58-219">StoreFunctionName</span><span class="sxs-lookup"><span data-stu-id="05d58-219">StoreFunctionName</span></span>|<span data-ttu-id="05d58-220">string</span><span class="sxs-lookup"><span data-stu-id="05d58-220">String</span></span>|<span data-ttu-id="05d58-221">Sin</span><span class="sxs-lookup"><span data-stu-id="05d58-221">No</span></span>|<span data-ttu-id="05d58-222">\<Nombre ></span><span class="sxs-lookup"><span data-stu-id="05d58-222">\<Name></span></span>|<span data-ttu-id="05d58-223">Nombre de la función en el almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="05d58-223">Function Name in the data store.</span></span>  <span data-ttu-id="05d58-224">Permite un nivel de redirección de nombres de función.</span><span class="sxs-lookup"><span data-stu-id="05d58-224">Allows for a level of redirection of function names.</span></span>|  
|<span data-ttu-id="05d58-225">NiladicFunction</span><span class="sxs-lookup"><span data-stu-id="05d58-225">NiladicFunction</span></span>|<span data-ttu-id="05d58-226">Boolean</span><span class="sxs-lookup"><span data-stu-id="05d58-226">Boolean</span></span>|<span data-ttu-id="05d58-227">Sin</span><span class="sxs-lookup"><span data-stu-id="05d58-227">No</span></span>|<span data-ttu-id="05d58-228">False</span><span class="sxs-lookup"><span data-stu-id="05d58-228">False</span></span>|<span data-ttu-id="05d58-229">True si la función no requiere parámetros y se invoca sin ningún parámetro</span><span class="sxs-lookup"><span data-stu-id="05d58-229">True if the function does not require parameters and is called without any parameters</span></span>|  
|<span data-ttu-id="05d58-230">ParameterType</span><span class="sxs-lookup"><span data-stu-id="05d58-230">ParameterType</span></span><br /><br /> <span data-ttu-id="05d58-231">Semántica</span><span class="sxs-lookup"><span data-stu-id="05d58-231">Semantics</span></span>|<span data-ttu-id="05d58-232">ParameterSemantics</span><span class="sxs-lookup"><span data-stu-id="05d58-232">ParameterSemantics</span></span>|<span data-ttu-id="05d58-233">Sin</span><span class="sxs-lookup"><span data-stu-id="05d58-233">No</span></span>|<span data-ttu-id="05d58-234">AllowImplicit</span><span class="sxs-lookup"><span data-stu-id="05d58-234">AllowImplicit</span></span><br /><br /> <span data-ttu-id="05d58-235">Conversión</span><span class="sxs-lookup"><span data-stu-id="05d58-235">Conversion</span></span>|<span data-ttu-id="05d58-236">Opción de cómo la canalización de la consulta debe tratar la sustitución de tipos de parámetro:</span><span class="sxs-lookup"><span data-stu-id="05d58-236">Choice of how the query pipeline should deal with parameter type substitution:</span></span><br /><br /> <span data-ttu-id="05d58-237">- ExactMatchOnly</span><span class="sxs-lookup"><span data-stu-id="05d58-237">-   ExactMatchOnly</span></span><br /><span data-ttu-id="05d58-238">-   AllowImplicitPromotion</span><span class="sxs-lookup"><span data-stu-id="05d58-238">-   AllowImplicitPromotion</span></span><br /><span data-ttu-id="05d58-239">-   AllowImplicitConversion</span><span class="sxs-lookup"><span data-stu-id="05d58-239">-   AllowImplicitConversion</span></span>|  
  
 <span data-ttu-id="05d58-240">**Nodo parámetros**</span><span class="sxs-lookup"><span data-stu-id="05d58-240">**Parameters Node**</span></span>  
  
 <span data-ttu-id="05d58-241">Cada función tiene una colección de uno o más nodos Parameter.</span><span class="sxs-lookup"><span data-stu-id="05d58-241">Each function has a collection of one or more Parameter nodes.</span></span>  
  
|<span data-ttu-id="05d58-242">Nombre de atributo</span><span class="sxs-lookup"><span data-stu-id="05d58-242">Attribute Name</span></span>|<span data-ttu-id="05d58-243">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="05d58-243">Data Type</span></span>|<span data-ttu-id="05d58-244">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="05d58-244">Required</span></span>|<span data-ttu-id="05d58-245">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="05d58-245">Default Value</span></span>|<span data-ttu-id="05d58-246">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="05d58-246">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="05d58-247">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="05d58-247">Name</span></span>|<span data-ttu-id="05d58-248">string</span><span class="sxs-lookup"><span data-stu-id="05d58-248">String</span></span>|<span data-ttu-id="05d58-249">Sí</span><span class="sxs-lookup"><span data-stu-id="05d58-249">Yes</span></span>|<span data-ttu-id="05d58-250">N/D</span><span class="sxs-lookup"><span data-stu-id="05d58-250">n/a</span></span>|<span data-ttu-id="05d58-251">Identificador/nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="05d58-251">Identifier/name of the parameter.</span></span>|  
|<span data-ttu-id="05d58-252">Type</span><span class="sxs-lookup"><span data-stu-id="05d58-252">Type</span></span>|<span data-ttu-id="05d58-253">string</span><span class="sxs-lookup"><span data-stu-id="05d58-253">String</span></span>|<span data-ttu-id="05d58-254">Sí</span><span class="sxs-lookup"><span data-stu-id="05d58-254">Yes</span></span>|<span data-ttu-id="05d58-255">N/D</span><span class="sxs-lookup"><span data-stu-id="05d58-255">n/a</span></span>|<span data-ttu-id="05d58-256">El tipo EDM del parámetro.</span><span class="sxs-lookup"><span data-stu-id="05d58-256">The EDM type of the parameter.</span></span>|  
|<span data-ttu-id="05d58-257">Mode</span><span class="sxs-lookup"><span data-stu-id="05d58-257">Mode</span></span>|<span data-ttu-id="05d58-258">Parámetro</span><span class="sxs-lookup"><span data-stu-id="05d58-258">Parameter</span></span><br /><br /> <span data-ttu-id="05d58-259">Direction</span><span class="sxs-lookup"><span data-stu-id="05d58-259">Direction</span></span>|<span data-ttu-id="05d58-260">Sí</span><span class="sxs-lookup"><span data-stu-id="05d58-260">Yes</span></span>|<span data-ttu-id="05d58-261">N/D</span><span class="sxs-lookup"><span data-stu-id="05d58-261">n/a</span></span>|<span data-ttu-id="05d58-262">Dirección del parámetro:</span><span class="sxs-lookup"><span data-stu-id="05d58-262">Direction of parameter:</span></span><br /><br /> <span data-ttu-id="05d58-263">-en</span><span class="sxs-lookup"><span data-stu-id="05d58-263">-   in</span></span><br /><span data-ttu-id="05d58-264">-out</span><span class="sxs-lookup"><span data-stu-id="05d58-264">-   out</span></span><br /><span data-ttu-id="05d58-265">-Inout</span><span class="sxs-lookup"><span data-stu-id="05d58-265">-   inout</span></span>|  
  
##### <a name="namespace-attribute"></a><span data-ttu-id="05d58-266">Atributo Namespace</span><span class="sxs-lookup"><span data-stu-id="05d58-266">Namespace Attribute</span></span>  
 <span data-ttu-id="05d58-267">Cada proveedor de almacén de datos debe definir un espacio de nombres o un grupo de espacios de nombres para la información definida en el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="05d58-267">Each data store provider must define a namespace or group of namespaces for information defined in the manifest.</span></span> <span data-ttu-id="05d58-268">Este espacio de nombres se puede utilizar en consultas de Entity SQL para resolver nombres de funciones y tipos.</span><span class="sxs-lookup"><span data-stu-id="05d58-268">This namespace can be used in Entity SQL queries to resolve names of functions and types.</span></span> <span data-ttu-id="05d58-269">Por ejemplo: Server.</span><span class="sxs-lookup"><span data-stu-id="05d58-269">For instance: SqlServer.</span></span> <span data-ttu-id="05d58-270">Ese espacio de nombres debe ser distinto del espacio de nombres canónico, EDM, definido por Servicios de entidad para que las consultas de Entity SQL admitan las funciones estándar.</span><span class="sxs-lookup"><span data-stu-id="05d58-270">That namespace must be different from the canonical namespace, EDM, defined by Entity Services for standard functions to be supported by Entity SQL queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d58-271">Vea también</span><span class="sxs-lookup"><span data-stu-id="05d58-271">See also</span></span>

- [<span data-ttu-id="05d58-272">Escritura de un proveedor de datos de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="05d58-272">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
