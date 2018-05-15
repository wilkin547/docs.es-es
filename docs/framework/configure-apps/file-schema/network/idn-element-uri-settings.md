---
title: '&lt;IDN&gt; elemento (configuración de Uri)'
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 17f68fbb92797928be911e530232e8638793687f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltidngt-element-uri-settings"></a><span data-ttu-id="c734a-102">&lt;IDN&gt; elemento (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="c734a-102">&lt;idn&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="c734a-103">Especifica si el análisis de nombre de dominio internacionalizado (IDN) se aplica a un nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="c734a-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="c734a-104">Jerarquía del esquema</span><span class="sxs-lookup"><span data-stu-id="c734a-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="c734a-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="c734a-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="c734a-106">\<URI > elemento (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="c734a-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="c734a-107">\<IDN ></span><span class="sxs-lookup"><span data-stu-id="c734a-107">\<idn></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="c734a-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c734a-108">Syntax</span></span>  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c734a-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c734a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c734a-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c734a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c734a-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c734a-111">Attributes</span></span>  
  
|<span data-ttu-id="c734a-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="c734a-112">**Element**</span></span>|<span data-ttu-id="c734a-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c734a-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="c734a-114">Especifica que si el análisis de nombre de dominio internacionalizado (IDN) se aplica a un nombre de dominio el valor predeterminado es none.</span><span class="sxs-lookup"><span data-stu-id="c734a-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c734a-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c734a-115">Child Elements</span></span>  
 <span data-ttu-id="c734a-116">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c734a-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c734a-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c734a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c734a-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="c734a-118">**Element**</span></span>|<span data-ttu-id="c734a-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c734a-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c734a-120">URI</span><span class="sxs-lookup"><span data-stu-id="c734a-120">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="c734a-121">Contiene valores que especifican cómo .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="c734a-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c734a-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c734a-122">Remarks</span></span>  
 <span data-ttu-id="c734a-123">Existente <xref:System.Uri> clase se ha extendido en .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="c734a-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="c734a-124">3.0 SP1 y 2.0 SP1 con compatibilidad con identificadores de recursos internacionales (IRI) y nombres de dominio internacionalizados (IDN).</span><span class="sxs-lookup"><span data-stu-id="c734a-124">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="c734a-125">Los usuarios actuales no verán ningún cambio del comportamiento de .NET Framework 2.0 a menos que habiliten específicamente IRI e IDN admite.</span><span class="sxs-lookup"><span data-stu-id="c734a-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="c734a-126">Esto garantiza la compatibilidad de las aplicaciones con versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c734a-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="c734a-127">Para habilitar la compatibilidad con IRI, son necesarios los siguientes dos cambios:</span><span class="sxs-lookup"><span data-stu-id="c734a-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1.  <span data-ttu-id="c734a-128">Agregue la siguiente línea al archivo machine.config en el directorio de .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="c734a-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  <span data-ttu-id="c734a-129">Especifique si desea analizar el nombre de dominio internacionalizado (IDN) aplica para el nombre de dominio y si se debe aplicar las reglas de análisis IRI.</span><span class="sxs-lookup"><span data-stu-id="c734a-129">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="c734a-130">Esto puede hacerse en el archivo machine.config o app.config.</span><span class="sxs-lookup"><span data-stu-id="c734a-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="c734a-131">Hay tres valores posibles para IDN según los servidores DNS que se utilizan:</span><span class="sxs-lookup"><span data-stu-id="c734a-131">There are three possible values for IDN depending on the DNS servers that are used:</span></span>  
  
-   <span data-ttu-id="c734a-132">IDN habilitada = All</span><span class="sxs-lookup"><span data-stu-id="c734a-132">idn enabled = All</span></span>  
  
     <span data-ttu-id="c734a-133">Este valor convertirá los nombres de dominio Unicode en su equivalente Punycode (nombres IDN).</span><span class="sxs-lookup"><span data-stu-id="c734a-133">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>  
  
-   <span data-ttu-id="c734a-134">IDN habilitada = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="c734a-134">idn enabled = AllExceptIntranet</span></span>  
  
     <span data-ttu-id="c734a-135">Este valor convertirá todos los nombres de dominio Unicode no estén en la Intranet local para que utilicen sus equivalentes Punycode (nombres IDN).</span><span class="sxs-lookup"><span data-stu-id="c734a-135">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="c734a-136">En este caso, para administrar los nombres internacionales en la Intranet local, los servidores DNS que se utilizan para la Intranet deben admitir la resolución de nombre de Unicode.</span><span class="sxs-lookup"><span data-stu-id="c734a-136">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>  
  
-   <span data-ttu-id="c734a-137">IDN habilitada = ninguno</span><span class="sxs-lookup"><span data-stu-id="c734a-137">idn enabled = None</span></span>  
  
     <span data-ttu-id="c734a-138">Este valor no convierte los nombres de dominio Unicode usar Punycode.</span><span class="sxs-lookup"><span data-stu-id="c734a-138">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="c734a-139">Este es el valor predeterminado que es coherente con el comportamiento de .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="c734a-139">This is the default value which is consistent with the .NET Framework 2.0 behaviour.</span></span>  
  
 <span data-ttu-id="c734a-140">La activación de IDN convertirá todas la etiquetas Unicode de un nombre de dominio en sus equivalentes de Punycode.</span><span class="sxs-lookup"><span data-stu-id="c734a-140">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="c734a-141">Los nombres de Punycode solo contienen caracteres ASCII y siempre empiezan con el prefijo xn--.</span><span class="sxs-lookup"><span data-stu-id="c734a-141">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="c734a-142">De este modo, se admiten los servidores DNS existentes en Internet, ya que la mayoría de los servidores DNS solo admite caracteres ASCII (vea RFC 3940).</span><span class="sxs-lookup"><span data-stu-id="c734a-142">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="c734a-143">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c734a-143">Configuration Files</span></span>  
 <span data-ttu-id="c734a-144">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c734a-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c734a-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c734a-145">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c734a-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="c734a-146">Description</span></span>  
 <span data-ttu-id="c734a-147">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir el análisis IRI y los nombres IDN.</span><span class="sxs-lookup"><span data-stu-id="c734a-147">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c734a-148">Código</span><span class="sxs-lookup"><span data-stu-id="c734a-148">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c734a-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="c734a-149">See Also</span></span>  
 <xref:System.Configuration.IdnElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [<span data-ttu-id="c734a-150">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="c734a-150">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
