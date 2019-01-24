---
title: '&lt;httpWebRequest&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: 1a883b2e57d0f055237d68e4f69651ef496795ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590040"
---
# <a name="lthttpwebrequestgt-element-network-settings"></a><span data-ttu-id="2d6df-102">&lt;httpWebRequest&gt; elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="2d6df-102">&lt;httpWebRequest&gt; Element (Network Settings)</span></span>
<span data-ttu-id="2d6df-103">Personaliza los parámetros de solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="2d6df-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="2d6df-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2d6df-104">\<configuration></span></span>  
<span data-ttu-id="2d6df-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="2d6df-105">\<system.net></span></span>  
<span data-ttu-id="2d6df-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="2d6df-106">\<settings></span></span>  
<span data-ttu-id="2d6df-107">\<httpWebRequest></span><span class="sxs-lookup"><span data-stu-id="2d6df-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d6df-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d6df-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d6df-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2d6df-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2d6df-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2d6df-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d6df-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="2d6df-111">Attributes</span></span>  
  
|<span data-ttu-id="2d6df-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="2d6df-112">**Attribute**</span></span>|<span data-ttu-id="2d6df-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2d6df-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="2d6df-114">Especifica la longitud máxima de un encabezado de respuesta, en kilobytes.</span><span class="sxs-lookup"><span data-stu-id="2d6df-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="2d6df-115">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="2d6df-115">The default is 64.</span></span> <span data-ttu-id="2d6df-116">El valor -1 indica que no se impondrá ningún límite de tamaño en los encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="2d6df-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="2d6df-117">Especifica la longitud máxima de una respuesta de error, en kilobytes.</span><span class="sxs-lookup"><span data-stu-id="2d6df-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="2d6df-118">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="2d6df-118">The default is 64.</span></span> <span data-ttu-id="2d6df-119">El valor -1 indica que no hay límite de tamaño se impondrá en la respuesta de error.</span><span class="sxs-lookup"><span data-stu-id="2d6df-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="2d6df-120">Especifica la longitud máxima de una carga en respuesta a un código de error no autorizado, en bytes.</span><span class="sxs-lookup"><span data-stu-id="2d6df-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="2d6df-121">El valor predeterminado es -1.</span><span class="sxs-lookup"><span data-stu-id="2d6df-121">The default is -1.</span></span> <span data-ttu-id="2d6df-122">El valor -1 indica que no hay límite de tamaño se impondrá en la carga.</span><span class="sxs-lookup"><span data-stu-id="2d6df-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="2d6df-123">Especifica si está habilitado el análisis de encabezado no segura.</span><span class="sxs-lookup"><span data-stu-id="2d6df-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="2d6df-124">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="2d6df-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d6df-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2d6df-125">Child Elements</span></span>  
 <span data-ttu-id="2d6df-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2d6df-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d6df-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2d6df-127">Parent Elements</span></span>  
  
|<span data-ttu-id="2d6df-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="2d6df-128">**Element**</span></span>|<span data-ttu-id="2d6df-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2d6df-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2d6df-130">settings</span><span class="sxs-lookup"><span data-stu-id="2d6df-130">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="2d6df-131">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="2d6df-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d6df-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d6df-132">Remarks</span></span>  
 <span data-ttu-id="2d6df-133">De forma predeterminada, .NET Framework aplica estrictamente RFC 2616 para analizar URI.</span><span class="sxs-lookup"><span data-stu-id="2d6df-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="2d6df-134">Algunas respuestas del servidor pueden incluir caracteres de control en campos prohibidos, lo que hará que el <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> método inicie una <xref:System.Net.WebException>.</span><span class="sxs-lookup"><span data-stu-id="2d6df-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="2d6df-135">Si **useUnsafeHeaderParsing** está establecido en **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> no iniciará ninguna en este caso; sin embargo, la aplicación será vulnerable a varias formas de ataques de análisis de URI.</span><span class="sxs-lookup"><span data-stu-id="2d6df-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="2d6df-136">La mejor solución es cambiar el servidor de modo que la respuesta no incluya caracteres de control.</span><span class="sxs-lookup"><span data-stu-id="2d6df-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2d6df-137">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="2d6df-137">Configuration Files</span></span>  
 <span data-ttu-id="2d6df-138">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2d6df-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d6df-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d6df-139">Example</span></span>  
 <span data-ttu-id="2d6df-140">El ejemplo siguiente muestra cómo especificar una mayor que la longitud máxima de encabezado normal.</span><span class="sxs-lookup"><span data-stu-id="2d6df-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d6df-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d6df-141">See also</span></span>
- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="2d6df-142">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="2d6df-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
