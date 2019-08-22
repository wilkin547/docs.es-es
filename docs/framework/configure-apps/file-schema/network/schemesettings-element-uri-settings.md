---
title: Elemento <schemeSettings> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 46012b15d41422fb3357e57438e320136809ef41
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664012"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="7d10b-102">\<schemeSettings > elemento (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="7d10b-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="7d10b-103">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="7d10b-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
 <span data-ttu-id="7d10b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7d10b-104">\<configuration></span></span>  
<span data-ttu-id="7d10b-105">\<Uri ></span><span class="sxs-lookup"><span data-stu-id="7d10b-105">\<uri></span></span>  
<span data-ttu-id="7d10b-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="7d10b-106">\<schemeSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d10b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d10b-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d10b-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7d10b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7d10b-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7d10b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d10b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="7d10b-110">Attributes</span></span>  
 <span data-ttu-id="7d10b-111">None</span><span class="sxs-lookup"><span data-stu-id="7d10b-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7d10b-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7d10b-112">Child Elements</span></span>  
  
|<span data-ttu-id="7d10b-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="7d10b-113">**Element**</span></span>|<span data-ttu-id="7d10b-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7d10b-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7d10b-115">add</span><span class="sxs-lookup"><span data-stu-id="7d10b-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="7d10b-116">Agrega una configuración de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="7d10b-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="7d10b-117">clear</span><span class="sxs-lookup"><span data-stu-id="7d10b-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="7d10b-118">Borra todos los valores de esquema existentes.</span><span class="sxs-lookup"><span data-stu-id="7d10b-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="7d10b-119">remove</span><span class="sxs-lookup"><span data-stu-id="7d10b-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="7d10b-120">Quita un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="7d10b-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d10b-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7d10b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7d10b-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="7d10b-122">**Element**</span></span>|<span data-ttu-id="7d10b-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7d10b-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7d10b-124">uri</span><span class="sxs-lookup"><span data-stu-id="7d10b-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="7d10b-125">Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="7d10b-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d10b-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d10b-126">Remarks</span></span>  
 <span data-ttu-id="7d10b-127">De forma predeterminada, <xref:System.Uri?displayProperty=nameWithType> la clase no escapa los delimitadores de ruta de acceso codificados por porcentaje antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7d10b-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="7d10b-128">Esto se implementó como un mecanismo de seguridad contra ataques como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d10b-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="7d10b-129">Si este URI se pasa a los módulos que no controlan correctamente los caracteres codificados por porcentaje, podría provocar que el servidor ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7d10b-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="7d10b-130">Por esta razón, <xref:System.Uri?displayProperty=nameWithType> la clase primero anula el escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7d10b-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="7d10b-131">El resultado de pasar la dirección URL malintencionada anterior <xref:System.Uri?displayProperty=nameWithType> al constructor de clase da como resultado el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="7d10b-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="7d10b-132">Este comportamiento predeterminado se puede modificar para que no se eliminen los delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="7d10b-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7d10b-133">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7d10b-133">Configuration Files</span></span>  
 <span data-ttu-id="7d10b-134">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="7d10b-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d10b-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d10b-135">Example</span></span>  
 <span data-ttu-id="7d10b-136">En el ejemplo siguiente se muestra una configuración utilizada <xref:System.Uri> por la clase para admitir delimitadores de ruta de acceso no codificados por porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="7d10b-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="7d10b-137">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="7d10b-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="7d10b-138">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="7d10b-138">Namespace</span></span>|<span data-ttu-id="7d10b-139">Sistema</span><span class="sxs-lookup"><span data-stu-id="7d10b-139">System</span></span>|  
|<span data-ttu-id="7d10b-140">Nombre de esquema</span><span class="sxs-lookup"><span data-stu-id="7d10b-140">Schema Name</span></span>||  
|<span data-ttu-id="7d10b-141">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="7d10b-141">Validation File</span></span>||  
|<span data-ttu-id="7d10b-142">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="7d10b-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="7d10b-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d10b-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="7d10b-144">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="7d10b-144">Network Settings Schema</span></span>](index.md)
