---
title: Elemento <schemeSettings> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 5a146b854239fd516125e66e05312e27b90c73ec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91187022"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="63f62-102">Elemento \<schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="63f62-102">\<schemeSettings> Element (Uri Settings)</span></span>

<span data-ttu-id="63f62-103">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="63f62-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="63f62-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63f62-104">Syntax</span></span>  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63f62-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="63f62-105">Attributes and Elements</span></span>  

 <span data-ttu-id="63f62-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="63f62-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63f62-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="63f62-107">Attributes</span></span>  

 <span data-ttu-id="63f62-108">None</span><span class="sxs-lookup"><span data-stu-id="63f62-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="63f62-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="63f62-109">Child Elements</span></span>  
  
|<span data-ttu-id="63f62-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="63f62-110">**Element**</span></span>|<span data-ttu-id="63f62-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="63f62-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="63f62-112">add</span><span class="sxs-lookup"><span data-stu-id="63f62-112">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="63f62-113">Agrega una configuración de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="63f62-113">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="63f62-114">clear</span><span class="sxs-lookup"><span data-stu-id="63f62-114">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="63f62-115">Borra todos los valores de esquema existentes.</span><span class="sxs-lookup"><span data-stu-id="63f62-115">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="63f62-116">remove</span><span class="sxs-lookup"><span data-stu-id="63f62-116">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="63f62-117">Quita un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="63f62-117">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="63f62-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="63f62-118">Parent Elements</span></span>  
  
|<span data-ttu-id="63f62-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="63f62-119">**Element**</span></span>|<span data-ttu-id="63f62-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="63f62-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="63f62-121">uri</span><span class="sxs-lookup"><span data-stu-id="63f62-121">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="63f62-122">Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="63f62-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63f62-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="63f62-123">Remarks</span></span>  

 <span data-ttu-id="63f62-124">De forma predeterminada, la <xref:System.Uri?displayProperty=nameWithType> clase no escapa los delimitadores de ruta de acceso codificados por porcentaje antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="63f62-124">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="63f62-125">Esto se implementó como un mecanismo de seguridad contra ataques como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="63f62-125">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="63f62-126">Si este URI se pasa a los módulos que no controlan correctamente los caracteres codificados por porcentaje, podría provocar que el servidor ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="63f62-126">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="63f62-127">Por esta razón, la <xref:System.Uri?displayProperty=nameWithType> clase primero anula el escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="63f62-127">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="63f62-128">El resultado de pasar la dirección URL malintencionada anterior al <xref:System.Uri?displayProperty=nameWithType> constructor de clase da como resultado el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="63f62-128">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="63f62-129">Este comportamiento predeterminado se puede modificar para que no se eliminen los delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="63f62-129">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="63f62-130">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="63f62-130">Configuration Files</span></span>  

 <span data-ttu-id="63f62-131">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="63f62-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="63f62-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63f62-132">Example</span></span>  

 <span data-ttu-id="63f62-133">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir delimitadores de ruta de acceso no codificados por porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="63f62-133">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="63f62-134">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="63f62-134">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="63f62-135">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="63f62-135">Namespace</span></span>|<span data-ttu-id="63f62-136">Sistema</span><span class="sxs-lookup"><span data-stu-id="63f62-136">System</span></span>|  
|<span data-ttu-id="63f62-137">Nombre del esquema</span><span class="sxs-lookup"><span data-stu-id="63f62-137">Schema Name</span></span>||  
|<span data-ttu-id="63f62-138">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="63f62-138">Validation File</span></span>||  
|<span data-ttu-id="63f62-139">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="63f62-139">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="63f62-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63f62-140">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="63f62-141">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="63f62-141">Network Settings Schema</span></span>](index.md)
