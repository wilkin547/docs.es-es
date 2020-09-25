---
title: Elemento <httpWebRequest> (configuración de red)
description: El <httpWebRequest> elemento de configuración de red Personaliza los parámetros de la solicitud Web en el .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: 86960a33d0924013e2bfbfa743eab372181033b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195433"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="441e9-103">Elemento \<httpWebRequest> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="441e9-103">\<httpWebRequest> Element (Network Settings)</span></span>

<span data-ttu-id="441e9-104">Personaliza los parámetros de la solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="441e9-104">Customizes Web request parameters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**

## <a name="syntax"></a><span data-ttu-id="441e9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="441e9-105">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="441e9-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="441e9-106">Attributes and Elements</span></span>  

 <span data-ttu-id="441e9-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="441e9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="441e9-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="441e9-108">Attributes</span></span>  
  
|<span data-ttu-id="441e9-109">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="441e9-109">**Attribute**</span></span>|<span data-ttu-id="441e9-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="441e9-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="441e9-111">Especifica la longitud máxima de un encabezado de respuesta, en kilobytes.</span><span class="sxs-lookup"><span data-stu-id="441e9-111">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="441e9-112">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="441e9-112">The default is 64.</span></span> <span data-ttu-id="441e9-113">Un valor de-1 indica que no se impondrá ningún límite de tamaño en los encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="441e9-113">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="441e9-114">Especifica la longitud máxima de una respuesta de error, en kilobytes.</span><span class="sxs-lookup"><span data-stu-id="441e9-114">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="441e9-115">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="441e9-115">The default is 64.</span></span> <span data-ttu-id="441e9-116">Un valor de-1 indica que no se impondrá ningún límite de tamaño en la respuesta de error.</span><span class="sxs-lookup"><span data-stu-id="441e9-116">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="441e9-117">Especifica la longitud máxima de una carga en respuesta a un código de error no autorizado, en bytes.</span><span class="sxs-lookup"><span data-stu-id="441e9-117">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="441e9-118">El valor predeterminado es -1.</span><span class="sxs-lookup"><span data-stu-id="441e9-118">The default is -1.</span></span> <span data-ttu-id="441e9-119">Un valor -1 indica que no se impondrá límite de tamaño a la carga.</span><span class="sxs-lookup"><span data-stu-id="441e9-119">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="441e9-120">Especifica si está habilitado el análisis de encabezados no seguros.</span><span class="sxs-lookup"><span data-stu-id="441e9-120">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="441e9-121">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="441e9-121">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="441e9-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="441e9-122">Child Elements</span></span>  

 <span data-ttu-id="441e9-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="441e9-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="441e9-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="441e9-124">Parent Elements</span></span>  
  
|<span data-ttu-id="441e9-125">**Element**</span><span class="sxs-lookup"><span data-stu-id="441e9-125">**Element**</span></span>|<span data-ttu-id="441e9-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="441e9-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="441e9-127">settings</span><span class="sxs-lookup"><span data-stu-id="441e9-127">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="441e9-128">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="441e9-128">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="441e9-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="441e9-129">Remarks</span></span>  

 <span data-ttu-id="441e9-130">De forma predeterminada, el .NET Framework aplica estrictamente la RFC 2616 para el análisis de URI.</span><span class="sxs-lookup"><span data-stu-id="441e9-130">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="441e9-131">Algunas respuestas del servidor pueden incluir caracteres de control en campos prohibidos, lo que hará que el <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> método produzca una excepción <xref:System.Net.WebException> .</span><span class="sxs-lookup"><span data-stu-id="441e9-131">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="441e9-132">Si **useUnsafeHeaderParsing** se establece en **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> no se producirá en este caso; sin embargo, la aplicación será vulnerable a varias formas de ataques de análisis de URI.</span><span class="sxs-lookup"><span data-stu-id="441e9-132">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="441e9-133">La mejor solución es cambiar el servidor para que la respuesta no incluya caracteres de control.</span><span class="sxs-lookup"><span data-stu-id="441e9-133">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="441e9-134">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="441e9-134">Configuration Files</span></span>  

 <span data-ttu-id="441e9-135">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="441e9-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="441e9-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="441e9-136">Example</span></span>  

 <span data-ttu-id="441e9-137">En el ejemplo siguiente se muestra cómo especificar una longitud de encabezado máxima mayor que la normal.</span><span class="sxs-lookup"><span data-stu-id="441e9-137">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="441e9-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="441e9-138">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="441e9-139">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="441e9-139">Network Settings Schema</span></span>](index.md)
