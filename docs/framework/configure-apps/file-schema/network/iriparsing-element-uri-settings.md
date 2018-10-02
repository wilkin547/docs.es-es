---
title: '&lt;iriParsing&gt; elemento (configuración de Uri)'
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 446447f0d279755dbc06e0e3a25d50ad86ad555b
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028293"
---
# <a name="ltiriparsinggt-element-uri-settings"></a><span data-ttu-id="16502-102">&lt;iriParsing&gt; elemento (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="16502-102">&lt;iriParsing&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="16502-103">Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="16502-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="16502-104">Jerarquía del esquema</span><span class="sxs-lookup"><span data-stu-id="16502-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="16502-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="16502-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="16502-106">\<URI > elemento (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="16502-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="16502-107">\<iriParsing ></span><span class="sxs-lookup"><span data-stu-id="16502-107">\<iriParsing></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="16502-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16502-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16502-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="16502-109">Attributes and Elements</span></span>  
 <span data-ttu-id="16502-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="16502-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16502-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="16502-111">Attributes</span></span>  
  
|<span data-ttu-id="16502-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="16502-112">**Element**</span></span>|<span data-ttu-id="16502-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="16502-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="16502-114">Especifica si está habilitado el análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="16502-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="16502-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="16502-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16502-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="16502-116">Child Elements</span></span>  
 <span data-ttu-id="16502-117">Ninguna</span><span class="sxs-lookup"><span data-stu-id="16502-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16502-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="16502-118">Parent Elements</span></span>  
  
|<span data-ttu-id="16502-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="16502-119">**Element**</span></span>|<span data-ttu-id="16502-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="16502-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="16502-121">Identificador URI</span><span class="sxs-lookup"><span data-stu-id="16502-121">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="16502-122">Contiene valores que especifican cómo .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="16502-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16502-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16502-123">Remarks</span></span>  
 <span data-ttu-id="16502-124">Existente <xref:System.Uri> se ha ampliado la clase en .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="16502-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="16502-125">3.0 SP1 y 2.0 SP1 para proporcionar compatibilidad con los identificadores de recursos internacionales (IRI) y los nombres de dominio internacionalizados (IDN).</span><span class="sxs-lookup"><span data-stu-id="16502-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="16502-126">Los usuarios actuales no verán ningún cambio respecto al comportamiento de .NET Framework 2.0, a menos que habiliten específicamente IRI e IDN admite.</span><span class="sxs-lookup"><span data-stu-id="16502-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="16502-127">Esto garantiza la compatibilidad de las aplicaciones con versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="16502-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="16502-128">Para habilitar la compatibilidad con IRI, se requieren los siguientes dos cambios:</span><span class="sxs-lookup"><span data-stu-id="16502-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1.  <span data-ttu-id="16502-129">Agregue la siguiente línea al archivo machine.config en el directorio de .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="16502-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  <span data-ttu-id="16502-130">Especifique si se debe aplicar las reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="16502-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="16502-131">Esto puede hacerse en el archivo machine.config o app.config.</span><span class="sxs-lookup"><span data-stu-id="16502-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="16502-132">Habilitar análisis de IRI (iriParsing habilitado = `true`) llevará a cabo normalización y reglas de carácter de comprobación en función de la última IRI en RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="16502-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="16502-133">El valor predeterminado es `false` y se la normalización y comprobación de acuerdo con RFC 2396 y RFC 3986 (para literales de IPv6) de caracteres.</span><span class="sxs-lookup"><span data-stu-id="16502-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="16502-134">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="16502-134">Configuration Files</span></span>  
 <span data-ttu-id="16502-135">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="16502-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="16502-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16502-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="16502-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="16502-137">Description</span></span>  
 <span data-ttu-id="16502-138">El ejemplo siguiente muestra una configuración utilizada por el <xref:System.Uri> clase para admitir el análisis de IRI y nombres de IDN.</span><span class="sxs-lookup"><span data-stu-id="16502-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="16502-139">Código</span><span class="sxs-lookup"><span data-stu-id="16502-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="16502-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="16502-140">See Also</span></span>  
 <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [<span data-ttu-id="16502-141">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="16502-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
