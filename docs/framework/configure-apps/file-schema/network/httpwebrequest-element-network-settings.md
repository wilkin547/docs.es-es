---
title: '&lt;httpWebRequest&gt; Element (Network Settings)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1d1dce38e5188824ba1412d3f2a285bd2304f147
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741973"
---
# <a name="lthttpwebrequestgt-element-network-settings"></a><span data-ttu-id="09f6f-102">&lt;httpWebRequest&gt; Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="09f6f-102">&lt;httpWebRequest&gt; Element (Network Settings)</span></span>
<span data-ttu-id="09f6f-103">Personaliza los parámetros de solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="09f6f-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="09f6f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="09f6f-104">\<configuration></span></span>  
<span data-ttu-id="09f6f-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="09f6f-105">\<system.net></span></span>  
<span data-ttu-id="09f6f-106">\<Configuración ></span><span class="sxs-lookup"><span data-stu-id="09f6f-106">\<settings></span></span>  
<span data-ttu-id="09f6f-107">\<httpWebRequest ></span><span class="sxs-lookup"><span data-stu-id="09f6f-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09f6f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09f6f-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09f6f-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="09f6f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="09f6f-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="09f6f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09f6f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="09f6f-111">Attributes</span></span>  
  
|<span data-ttu-id="09f6f-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="09f6f-112">**Attribute**</span></span>|<span data-ttu-id="09f6f-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="09f6f-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="09f6f-114">Especifica la longitud máxima de un encabezado de respuesta, en kilobytes.</span><span class="sxs-lookup"><span data-stu-id="09f6f-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="09f6f-115">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="09f6f-115">The default is 64.</span></span> <span data-ttu-id="09f6f-116">Un valor de -1 indica que no va a imponerse ningún límite de tamaño de los encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="09f6f-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="09f6f-117">Especifica la longitud máxima de una respuesta de error, en kilobytes.</span><span class="sxs-lookup"><span data-stu-id="09f6f-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="09f6f-118">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="09f6f-118">The default is 64.</span></span> <span data-ttu-id="09f6f-119">Un valor de -1 indica que no va a imponerse ningún límite de tamaño en la respuesta de error.</span><span class="sxs-lookup"><span data-stu-id="09f6f-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="09f6f-120">Especifica la longitud máxima de una carga en respuesta a un código de error no autorizado, en bytes.</span><span class="sxs-lookup"><span data-stu-id="09f6f-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="09f6f-121">El valor predeterminado es -1.</span><span class="sxs-lookup"><span data-stu-id="09f6f-121">The default is -1.</span></span> <span data-ttu-id="09f6f-122">Un valor de -1 indica que no va a imponerse ningún límite de tamaño en la carga.</span><span class="sxs-lookup"><span data-stu-id="09f6f-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="09f6f-123">Especifica si está habilitado el análisis de encabezado no seguro.</span><span class="sxs-lookup"><span data-stu-id="09f6f-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="09f6f-124">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="09f6f-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09f6f-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="09f6f-125">Child Elements</span></span>  
 <span data-ttu-id="09f6f-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="09f6f-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="09f6f-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="09f6f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="09f6f-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="09f6f-128">**Element**</span></span>|<span data-ttu-id="09f6f-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="09f6f-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="09f6f-130">Configuración</span><span class="sxs-lookup"><span data-stu-id="09f6f-130">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="09f6f-131">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="09f6f-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09f6f-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="09f6f-132">Remarks</span></span>  
 <span data-ttu-id="09f6f-133">De manera predeterminada, .NET Framework aplica estrictamente RFC 2616 para analizar URI.</span><span class="sxs-lookup"><span data-stu-id="09f6f-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="09f6f-134">Algunas respuestas del servidor pueden incluir caracteres de control en campos prohibidos, lo que hará que la <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> método produzca un <xref:System.Net.WebException>.</span><span class="sxs-lookup"><span data-stu-id="09f6f-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="09f6f-135">Si **useUnsafeHeaderParsing** está establecido en **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> no se producirá en este caso; sin embargo, la aplicación será vulnerable a varios formatos de ataques de análisis de URI.</span><span class="sxs-lookup"><span data-stu-id="09f6f-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="09f6f-136">La mejor solución es cambiar el servidor de modo que la respuesta no incluya caracteres de control.</span><span class="sxs-lookup"><span data-stu-id="09f6f-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="09f6f-137">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="09f6f-137">Configuration Files</span></span>  
 <span data-ttu-id="09f6f-138">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="09f6f-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="09f6f-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09f6f-139">Example</span></span>  
 <span data-ttu-id="09f6f-140">En el ejemplo siguiente se muestra cómo especificar una mayor que la longitud máxima de encabezado normal.</span><span class="sxs-lookup"><span data-stu-id="09f6f-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="09f6f-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="09f6f-141">See Also</span></span>  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>  
 [<span data-ttu-id="09f6f-142">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="09f6f-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
