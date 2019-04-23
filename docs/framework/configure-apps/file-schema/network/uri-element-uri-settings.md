---
title: Elemento <Uri> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 1f3573babd2e363a78f0ad454f0ba36c87ba6390
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212148"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="cbd3d-102">\<URI > elemento (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="cbd3d-102">\<Uri> Element (Uri Settings)</span></span>
<span data-ttu-id="cbd3d-103">Contiene valores que especifican cómo .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="cbd3d-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="cbd3d-104">Jerarquía del esquema</span><span class="sxs-lookup"><span data-stu-id="cbd3d-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="cbd3d-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="cbd3d-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="cbd3d-106">\<uri></span><span class="sxs-lookup"><span data-stu-id="cbd3d-106">\<uri></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="cbd3d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cbd3d-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cbd3d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cbd3d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cbd3d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cbd3d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cbd3d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="cbd3d-110">Attributes</span></span>  
 <span data-ttu-id="cbd3d-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cbd3d-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cbd3d-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cbd3d-112">Child Elements</span></span>  
  
|<span data-ttu-id="cbd3d-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="cbd3d-113">**Element**</span></span>|<span data-ttu-id="cbd3d-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="cbd3d-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cbd3d-115">idn</span><span class="sxs-lookup"><span data-stu-id="cbd3d-115">idn</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="cbd3d-116">Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="cbd3d-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="cbd3d-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="cbd3d-117">iriParsing</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="cbd3d-118">Especifica si el análisis de identificadores de recursos internacionales (IRI) se aplica a <xref:System.Uri> y si debe aplicarse las reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="cbd3d-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="cbd3d-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="cbd3d-119">schemeSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="cbd3d-120">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="cbd3d-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cbd3d-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cbd3d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cbd3d-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="cbd3d-122">**Element**</span></span>|<span data-ttu-id="cbd3d-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="cbd3d-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cbd3d-124">configuration</span><span class="sxs-lookup"><span data-stu-id="cbd3d-124">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="cbd3d-125">Contiene la configuración para todos los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="cbd3d-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbd3d-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cbd3d-126">Remarks</span></span>  
 <span data-ttu-id="cbd3d-127">El `uri` elemento contiene los valores para los miembros de la <xref:System.Uri> clase usada por las clases en el <xref:System.Net> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="cbd3d-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="cbd3d-128">Configura la configuración de la compatibilidad con IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="cbd3d-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbd3d-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbd3d-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cbd3d-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="cbd3d-130">Description</span></span>  
 <span data-ttu-id="cbd3d-131">El ejemplo siguiente muestra una configuración utilizada por el <xref:System.Uri> clase para admitir el análisis de IRI y nombres de IDN.</span><span class="sxs-lookup"><span data-stu-id="cbd3d-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="cbd3d-132">El ejemplo también borra todos los valores de esquema y, a continuación, agrega compatibilidad para delimitadores de ruta de acceso codificados con porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="cbd3d-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cbd3d-133">Código</span><span class="sxs-lookup"><span data-stu-id="cbd3d-133">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cbd3d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbd3d-134">See also</span></span>

- [<span data-ttu-id="cbd3d-135">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="cbd3d-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
