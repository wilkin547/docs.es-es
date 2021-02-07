---
description: 'Más información sobre: <iriParsing> elemento (configuración de URI)'
title: Elemento <iriParsing> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: 460216b64056cd9c9f769c5bcd1b651d249e98b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740306"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="6322c-103">Elemento \<iriParsing> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="6322c-103">\<iriParsing> Element (Uri Settings)</span></span>

<span data-ttu-id="6322c-104">Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="6322c-104">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**  
  
## <a name="syntax"></a><span data-ttu-id="6322c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6322c-105">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6322c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6322c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="6322c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6322c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6322c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="6322c-108">Attributes</span></span>  
  
|<span data-ttu-id="6322c-109">**Element**</span><span class="sxs-lookup"><span data-stu-id="6322c-109">**Element**</span></span>|<span data-ttu-id="6322c-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6322c-110">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="6322c-111">Especifica si está habilitado el análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="6322c-111">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="6322c-112">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="6322c-112">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6322c-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6322c-113">Child Elements</span></span>  

 <span data-ttu-id="6322c-114">None</span><span class="sxs-lookup"><span data-stu-id="6322c-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6322c-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6322c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6322c-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="6322c-116">**Element**</span></span>|<span data-ttu-id="6322c-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6322c-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6322c-118">uri</span><span class="sxs-lookup"><span data-stu-id="6322c-118">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="6322c-119">Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="6322c-119">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6322c-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6322c-120">Remarks</span></span>  

 <span data-ttu-id="6322c-121">La clase existente se ha <xref:System.Uri> ampliado en .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="6322c-121">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="6322c-122">3,0 SP1 y 2,0 SP1 para proporcionar compatibilidad con los identificadores de recursos internacionales (IRI) y los nombres de dominio internacionalizados (IDN).</span><span class="sxs-lookup"><span data-stu-id="6322c-122">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="6322c-123">Los usuarios actuales no verán ningún cambio en el comportamiento de .NET Framework 2,0 a menos que habiliten específicamente la compatibilidad con IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="6322c-123">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="6322c-124">Esto garantiza la compatibilidad de las aplicaciones con versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6322c-124">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="6322c-125">Para habilitar la compatibilidad con IRI, se necesitan los dos cambios siguientes:</span><span class="sxs-lookup"><span data-stu-id="6322c-125">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="6322c-126">Agregue la siguiente línea al archivo machine.config en el directorio .NET Framework 2,0</span><span class="sxs-lookup"><span data-stu-id="6322c-126">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="6322c-127">Especifique si deben aplicarse las reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="6322c-127">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="6322c-128">Esto puede hacerse en el archivo machine.config o app.config.</span><span class="sxs-lookup"><span data-stu-id="6322c-128">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="6322c-129">Al habilitar el análisis de IRI (Análisisiri Enabled = `true` ), se realizará la normalización y la comprobación de caracteres según las reglas de IRI más recientes en RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="6322c-129">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="6322c-130">El valor predeterminado es `false` y realizará la normalización y la comprobación de caracteres según rfc 2396 y rfc 3986 (para los literales de IPv6).</span><span class="sxs-lookup"><span data-stu-id="6322c-130">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="6322c-131">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="6322c-131">Configuration Files</span></span>  

 <span data-ttu-id="6322c-132">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="6322c-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6322c-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6322c-133">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6322c-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="6322c-134">Description</span></span>  

 <span data-ttu-id="6322c-135">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir el análisis de IRI y los nombres IDN.</span><span class="sxs-lookup"><span data-stu-id="6322c-135">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6322c-136">Código</span><span class="sxs-lookup"><span data-stu-id="6322c-136">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6322c-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6322c-137">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="6322c-138">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="6322c-138">Network Settings Schema</span></span>](index.md)
