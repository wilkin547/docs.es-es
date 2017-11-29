---
title: "&lt;Análisisiri&gt; elemento (configuración de Uri)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: aad2ea9a9255a6fc11465bae92f693065db21cb3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltiriparsinggt-element-uri-settings"></a><span data-ttu-id="a865e-102">&lt;Análisisiri&gt; elemento (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="a865e-102">&lt;iriParsing&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="a865e-103">Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="a865e-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="a865e-104">Jerarquía del esquema</span><span class="sxs-lookup"><span data-stu-id="a865e-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="a865e-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="a865e-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="a865e-106">\<URI > elemento (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="a865e-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="a865e-107">\<Análisisiri ></span><span class="sxs-lookup"><span data-stu-id="a865e-107">\<iriParsing></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="a865e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a865e-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a865e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a865e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a865e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a865e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a865e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="a865e-111">Attributes</span></span>  
  
|<span data-ttu-id="a865e-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="a865e-112">**Element**</span></span>|<span data-ttu-id="a865e-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a865e-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="a865e-114">Especifica si está habilitado el análisis IRI.</span><span class="sxs-lookup"><span data-stu-id="a865e-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="a865e-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="a865e-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a865e-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a865e-116">Child Elements</span></span>  
 <span data-ttu-id="a865e-117">Ninguna</span><span class="sxs-lookup"><span data-stu-id="a865e-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a865e-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a865e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a865e-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="a865e-119">**Element**</span></span>|<span data-ttu-id="a865e-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a865e-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a865e-121">URI</span><span class="sxs-lookup"><span data-stu-id="a865e-121">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="a865e-122">Contiene valores que especifican cómo .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="a865e-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a865e-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a865e-123">Remarks</span></span>  
 <span data-ttu-id="a865e-124">Existente <xref:System.Uri> clase se ha extendido en .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="a865e-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="a865e-125">3.0 SP1 y 2.0 SP1 para proporcionar compatibilidad con identificadores de recursos internacionales (IRI) y nombres de dominio internacionalizados (IDN).</span><span class="sxs-lookup"><span data-stu-id="a865e-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="a865e-126">Los usuarios actuales no verán ningún cambio del comportamiento de .NET Framework 2.0 a menos que habiliten específicamente IRI e IDN admite.</span><span class="sxs-lookup"><span data-stu-id="a865e-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="a865e-127">Esto garantiza la compatibilidad de las aplicaciones con versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a865e-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="a865e-128">Para habilitar la compatibilidad con IRI, son necesarios los siguientes dos cambios:</span><span class="sxs-lookup"><span data-stu-id="a865e-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1.  <span data-ttu-id="a865e-129">Agregue la siguiente línea al archivo machine.config en el directorio de .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="a865e-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  <span data-ttu-id="a865e-130">Especifique si se debe aplicar las reglas de análisis IRI.</span><span class="sxs-lookup"><span data-stu-id="a865e-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="a865e-131">Esto puede hacerse en el archivo machine.config o app.config.</span><span class="sxs-lookup"><span data-stu-id="a865e-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="a865e-132">Habilitar el análisis IRI (Análisisiri habilitada = `true`) realizará la normalización y las reglas de comprobación según el IRI más reciente de caracteres en el documento RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="a865e-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="a865e-133">El valor predeterminado es `false` y se la normalización y caracteres de comprobación en función de RFC 2396 y RFC 3986 (para literales de IPv6).</span><span class="sxs-lookup"><span data-stu-id="a865e-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="a865e-134">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a865e-134">Configuration Files</span></span>  
 <span data-ttu-id="a865e-135">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a865e-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a865e-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a865e-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a865e-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="a865e-137">Description</span></span>  
 <span data-ttu-id="a865e-138">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir el análisis IRI y los nombres IDN.</span><span class="sxs-lookup"><span data-stu-id="a865e-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a865e-139">Código</span><span class="sxs-lookup"><span data-stu-id="a865e-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a865e-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="a865e-140">See Also</span></span>  
 <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [<span data-ttu-id="a865e-141">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="a865e-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
