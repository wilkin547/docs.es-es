---
title: Elemento <httpWebRequest> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: d33dadc14510feb00e05ca557b507b0cf8fa0dd0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087458"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="155d1-102">Elemento \<httpWebRequest> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="155d1-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="155d1-103">Personaliza los parámetros de la solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="155d1-103">Customizes Web request parameters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**

## <a name="syntax"></a><span data-ttu-id="155d1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="155d1-104">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="155d1-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="155d1-105">Attributes and Elements</span></span>  
 <span data-ttu-id="155d1-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="155d1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="155d1-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="155d1-107">Attributes</span></span>  
  
|<span data-ttu-id="155d1-108">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="155d1-108">**Attribute**</span></span>|<span data-ttu-id="155d1-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="155d1-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="155d1-110">Especifica la longitud máxima de un encabezado de respuesta, en kilobytes.</span><span class="sxs-lookup"><span data-stu-id="155d1-110">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="155d1-111">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="155d1-111">The default is 64.</span></span> <span data-ttu-id="155d1-112">Un valor de-1 indica que no se impondrá ningún límite de tamaño en los encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="155d1-112">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="155d1-113">Especifica la longitud máxima de una respuesta de error, en kilobytes.</span><span class="sxs-lookup"><span data-stu-id="155d1-113">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="155d1-114">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="155d1-114">The default is 64.</span></span> <span data-ttu-id="155d1-115">Un valor de-1 indica que no se impondrá ningún límite de tamaño en la respuesta de error.</span><span class="sxs-lookup"><span data-stu-id="155d1-115">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="155d1-116">Especifica la longitud máxima de una carga en respuesta a un código de error no autorizado, en bytes.</span><span class="sxs-lookup"><span data-stu-id="155d1-116">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="155d1-117">El valor predeterminado es -1.</span><span class="sxs-lookup"><span data-stu-id="155d1-117">The default is -1.</span></span> <span data-ttu-id="155d1-118">Un valor -1 indica que no se impondrá límite de tamaño a la carga.</span><span class="sxs-lookup"><span data-stu-id="155d1-118">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="155d1-119">Especifica si está habilitado el análisis de encabezados no seguros.</span><span class="sxs-lookup"><span data-stu-id="155d1-119">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="155d1-120">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="155d1-120">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="155d1-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="155d1-121">Child Elements</span></span>  
 <span data-ttu-id="155d1-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="155d1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="155d1-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="155d1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="155d1-124">**Element**</span><span class="sxs-lookup"><span data-stu-id="155d1-124">**Element**</span></span>|<span data-ttu-id="155d1-125">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="155d1-125">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="155d1-126">settings</span><span class="sxs-lookup"><span data-stu-id="155d1-126">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="155d1-127">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="155d1-127">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="155d1-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="155d1-128">Remarks</span></span>  
 <span data-ttu-id="155d1-129">De forma predeterminada, el .NET Framework aplica estrictamente la RFC 2616 para el análisis de URI.</span><span class="sxs-lookup"><span data-stu-id="155d1-129">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="155d1-130">Algunas respuestas del servidor pueden incluir caracteres de control en campos prohibidos, lo que hará que el <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> método produzca una excepción <xref:System.Net.WebException> .</span><span class="sxs-lookup"><span data-stu-id="155d1-130">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="155d1-131">Si **useUnsafeHeaderParsing** se establece en **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> no se producirá en este caso; sin embargo, la aplicación será vulnerable a varias formas de ataques de análisis de URI.</span><span class="sxs-lookup"><span data-stu-id="155d1-131">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="155d1-132">La mejor solución es cambiar el servidor para que la respuesta no incluya caracteres de control.</span><span class="sxs-lookup"><span data-stu-id="155d1-132">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="155d1-133">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="155d1-133">Configuration Files</span></span>  
 <span data-ttu-id="155d1-134">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="155d1-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="155d1-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="155d1-135">Example</span></span>  
 <span data-ttu-id="155d1-136">En el ejemplo siguiente se muestra cómo especificar una longitud de encabezado máxima mayor que la normal.</span><span class="sxs-lookup"><span data-stu-id="155d1-136">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="155d1-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="155d1-137">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="155d1-138">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="155d1-138">Network Settings Schema</span></span>](index.md)
