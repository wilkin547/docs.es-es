---
title: Elemento <servicePointManager> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: b7333016fea2d46285d3c98181c0ca4904c376f8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089126"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="a3634-102">Elemento \<servicePointManager> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="a3634-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="a3634-103">Configura las conexiones a los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="a3634-103">Configures connections to network resources.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**

## <a name="syntax"></a><span data-ttu-id="a3634-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3634-104">Syntax</span></span>  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3634-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a3634-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a3634-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a3634-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3634-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="a3634-107">Attributes</span></span>  
  
|<span data-ttu-id="a3634-108">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="a3634-108">**Attribute**</span></span>|<span data-ttu-id="a3634-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a3634-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="a3634-110">Especifica si el sistema debe comprobar que el nombre del certificado coincide con el nombre de host del servidor antes de usar el certificado.</span><span class="sxs-lookup"><span data-stu-id="a3634-110">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="a3634-111">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="a3634-111">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="a3634-112">Especifica si el sistema debe comprobar si el certificado se ha revocado antes de utilizar el certificado.</span><span class="sxs-lookup"><span data-stu-id="a3634-112">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="a3634-113">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="a3634-113">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="a3634-114">Especifica cuánto tiempo se almacenan en caché las resoluciones del servicio de nombres de dominio (DNS) junto con la opción Round Robin de DNS, en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="a3634-114">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="a3634-115">El valor predeterminado es 120.000 milisegundos (dos minutos).</span><span class="sxs-lookup"><span data-stu-id="a3634-115">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="a3634-116">Especifica si las resoluciones DNS de los nombres de host con varias direcciones IP (Protocolo de Internet) devuelven todas las direcciones, o solo la primera.</span><span class="sxs-lookup"><span data-stu-id="a3634-116">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="a3634-117">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="a3634-117">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="a3634-118">Especifica la Directiva de cifrado que se aplica a una sesión de SSL/TLS en una <xref:System.Net.ServicePointManager> instancia de.</span><span class="sxs-lookup"><span data-stu-id="a3634-118">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="a3634-119">Los valores posibles son equivalentes a los valores de la <xref:System.Net.Security.EncryptionPolicy> enumeración.</span><span class="sxs-lookup"><span data-stu-id="a3634-119">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="a3634-120">El uso de <xref:System.Security.Authentication.CipherAlgorithmType.Null> es necesario cuando la Directiva de cifrado se establece en `NoEncryption` .</span><span class="sxs-lookup"><span data-stu-id="a3634-120">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="a3634-121">El valor predeterminado es `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="a3634-121">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="a3634-122">Especifica si los métodos POST deben esperar recibir una `100-continue` respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="a3634-122">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="a3634-123">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="a3634-123">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="a3634-124">Especifica si las conexiones controladas por el administrador de puntos de servicio usan el algoritmo de Nagle.</span><span class="sxs-lookup"><span data-stu-id="a3634-124">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="a3634-125">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="a3634-125">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3634-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a3634-126">Child Elements</span></span>  
 <span data-ttu-id="a3634-127">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a3634-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3634-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a3634-128">Parent Elements</span></span>  
  
|<span data-ttu-id="a3634-129">**Element**</span><span class="sxs-lookup"><span data-stu-id="a3634-129">**Element**</span></span>|<span data-ttu-id="a3634-130">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a3634-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a3634-131">Configuración</span><span class="sxs-lookup"><span data-stu-id="a3634-131">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="a3634-132">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="a3634-132">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3634-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a3634-133">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a3634-134">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a3634-134">Configuration Files</span></span>  
 <span data-ttu-id="a3634-135">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a3634-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3634-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3634-136">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="a3634-137">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="a3634-137">Network Settings Schema</span></span>](index.md)
