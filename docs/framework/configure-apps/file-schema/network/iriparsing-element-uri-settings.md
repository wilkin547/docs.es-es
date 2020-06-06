---
title: Elemento <iriParsing> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: fd617d1b4ac8e532c6f9aeaa01465e9866b059e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698091"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="30fd6-102">Elemento \<iriParsing> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="30fd6-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="30fd6-103">Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="30fd6-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**  
  
## <a name="syntax"></a><span data-ttu-id="30fd6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30fd6-104">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30fd6-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="30fd6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="30fd6-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="30fd6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30fd6-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="30fd6-107">Attributes</span></span>  
  
|<span data-ttu-id="30fd6-108">**Element**</span><span class="sxs-lookup"><span data-stu-id="30fd6-108">**Element**</span></span>|<span data-ttu-id="30fd6-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="30fd6-109">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="30fd6-110">Especifica si está habilitado el análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="30fd6-110">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="30fd6-111">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="30fd6-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30fd6-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="30fd6-112">Child Elements</span></span>  
 <span data-ttu-id="30fd6-113">None</span><span class="sxs-lookup"><span data-stu-id="30fd6-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30fd6-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="30fd6-114">Parent Elements</span></span>  
  
|<span data-ttu-id="30fd6-115">**Element**</span><span class="sxs-lookup"><span data-stu-id="30fd6-115">**Element**</span></span>|<span data-ttu-id="30fd6-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="30fd6-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="30fd6-117">uri</span><span class="sxs-lookup"><span data-stu-id="30fd6-117">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="30fd6-118">Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="30fd6-118">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30fd6-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="30fd6-119">Remarks</span></span>  
 <span data-ttu-id="30fd6-120">La clase existente se ha <xref:System.Uri> ampliado en .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="30fd6-120">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="30fd6-121">3,0 SP1 y 2,0 SP1 para proporcionar compatibilidad con los identificadores de recursos internacionales (IRI) y los nombres de dominio internacionalizados (IDN).</span><span class="sxs-lookup"><span data-stu-id="30fd6-121">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="30fd6-122">Los usuarios actuales no verán ningún cambio en el comportamiento de .NET Framework 2,0 a menos que habiliten específicamente la compatibilidad con IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="30fd6-122">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="30fd6-123">Esto garantiza la compatibilidad de las aplicaciones con versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="30fd6-123">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="30fd6-124">Para habilitar la compatibilidad con IRI, se necesitan los dos cambios siguientes:</span><span class="sxs-lookup"><span data-stu-id="30fd6-124">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="30fd6-125">Agregue la siguiente línea al archivo Machine. config en el directorio .NET Framework 2,0</span><span class="sxs-lookup"><span data-stu-id="30fd6-125">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="30fd6-126">Especifique si deben aplicarse las reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="30fd6-126">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="30fd6-127">Esto puede hacerse en el archivo machine.config o app.config.</span><span class="sxs-lookup"><span data-stu-id="30fd6-127">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="30fd6-128">Al habilitar el análisis de IRI (Análisisiri Enabled = `true` ), se realizará la normalización y la comprobación de caracteres según las reglas de IRI más recientes en RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="30fd6-128">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="30fd6-129">El valor predeterminado es `false` y realizará la normalización y la comprobación de caracteres según rfc 2396 y rfc 3986 (para los literales de IPv6).</span><span class="sxs-lookup"><span data-stu-id="30fd6-129">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="30fd6-130">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="30fd6-130">Configuration Files</span></span>  
 <span data-ttu-id="30fd6-131">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="30fd6-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="30fd6-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30fd6-132">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="30fd6-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="30fd6-133">Description</span></span>  
 <span data-ttu-id="30fd6-134">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir el análisis de IRI y los nombres IDN.</span><span class="sxs-lookup"><span data-stu-id="30fd6-134">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="30fd6-135">Código</span><span class="sxs-lookup"><span data-stu-id="30fd6-135">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="30fd6-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="30fd6-136">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="30fd6-137">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="30fd6-137">Network Settings Schema</span></span>](index.md)
