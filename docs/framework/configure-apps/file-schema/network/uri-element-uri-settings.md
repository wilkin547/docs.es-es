---
title: "&lt;URI&gt; elemento (configuración de Uri)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 44ef28ca2188973ccd353f4e8615c7c95f5674a2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="lturigt-element-uri-settings"></a><span data-ttu-id="59892-102">&lt;URI&gt; elemento (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="59892-102">&lt;Uri&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="59892-103">Contiene valores que especifican cómo .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="59892-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="59892-104">Jerarquía del esquema</span><span class="sxs-lookup"><span data-stu-id="59892-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="59892-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="59892-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="59892-106">\<URI ></span><span class="sxs-lookup"><span data-stu-id="59892-106">\<uri></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="59892-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59892-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59892-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="59892-108">Attributes and Elements</span></span>  
 <span data-ttu-id="59892-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="59892-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59892-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="59892-110">Attributes</span></span>  
 <span data-ttu-id="59892-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="59892-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="59892-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="59892-112">Child Elements</span></span>  
  
|<span data-ttu-id="59892-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="59892-113">**Element**</span></span>|<span data-ttu-id="59892-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="59892-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="59892-115">IDN</span><span class="sxs-lookup"><span data-stu-id="59892-115">idn</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="59892-116">Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="59892-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="59892-117">Análisisiri</span><span class="sxs-lookup"><span data-stu-id="59892-117">iriParsing</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="59892-118">Especifica si el análisis de identificadores de recursos internacionales (IRI) se aplica a <xref:System.Uri> y si se debe aplicar las reglas de análisis IRI.</span><span class="sxs-lookup"><span data-stu-id="59892-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="59892-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="59892-119">schemeSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="59892-120">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="59892-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59892-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="59892-121">Parent Elements</span></span>  
  
|<span data-ttu-id="59892-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="59892-122">**Element**</span></span>|<span data-ttu-id="59892-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="59892-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="59892-124">configuración</span><span class="sxs-lookup"><span data-stu-id="59892-124">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="59892-125">Contiene valores para todos los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="59892-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59892-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="59892-126">Remarks</span></span>  
 <span data-ttu-id="59892-127">El `uri` elemento contiene los valores para los miembros de la <xref:System.Uri> clase utilizada por clases en el <xref:System.Net> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="59892-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="59892-128">La configuración de configura la compatibilidad con IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="59892-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59892-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="59892-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="59892-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="59892-130">Description</span></span>  
 <span data-ttu-id="59892-131">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir el análisis IRI y los nombres IDN.</span><span class="sxs-lookup"><span data-stu-id="59892-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="59892-132">El ejemplo también borra todos los valores de esquema y, a continuación, agrega compatibilidad para delimitadores de ruta de acceso con codificación de porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="59892-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="59892-133">Código</span><span class="sxs-lookup"><span data-stu-id="59892-133">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="59892-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="59892-134">See Also</span></span>  
 [<span data-ttu-id="59892-135">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="59892-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
