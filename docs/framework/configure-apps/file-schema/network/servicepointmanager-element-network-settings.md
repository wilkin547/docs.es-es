---
title: Elemento <servicePointManager> (configuración de red)
description: El <servicePointManager> elemento configuración de red configura las conexiones a las opciones de recursos de red en el .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: a6678a8fe7c6f962529f9d946b103b6224d58602
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174113"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="83664-103">Elemento \<servicePointManager> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="83664-103">\<servicePointManager> Element (Network Settings)</span></span>

<span data-ttu-id="83664-104">Configura las conexiones a los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="83664-104">Configures connections to network resources.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**

## <a name="syntax"></a><span data-ttu-id="83664-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83664-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83664-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="83664-106">Attributes and Elements</span></span>  

 <span data-ttu-id="83664-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="83664-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83664-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="83664-108">Attributes</span></span>  
  
|<span data-ttu-id="83664-109">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="83664-109">**Attribute**</span></span>|<span data-ttu-id="83664-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="83664-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="83664-111">Especifica si el sistema debe comprobar que el nombre del certificado coincide con el nombre de host del servidor antes de usar el certificado.</span><span class="sxs-lookup"><span data-stu-id="83664-111">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="83664-112">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="83664-112">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="83664-113">Especifica si el sistema debe comprobar si el certificado se ha revocado antes de utilizar el certificado.</span><span class="sxs-lookup"><span data-stu-id="83664-113">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="83664-114">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="83664-114">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="83664-115">Especifica cuánto tiempo se almacenan en caché las resoluciones del servicio de nombres de dominio (DNS) junto con la opción Round Robin de DNS, en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="83664-115">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="83664-116">El valor predeterminado es 120.000 milisegundos (dos minutos).</span><span class="sxs-lookup"><span data-stu-id="83664-116">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="83664-117">Especifica si las resoluciones DNS de los nombres de host con varias direcciones IP (Protocolo de Internet) devuelven todas las direcciones, o solo la primera.</span><span class="sxs-lookup"><span data-stu-id="83664-117">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="83664-118">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="83664-118">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="83664-119">Especifica la Directiva de cifrado que se aplica a una sesión de SSL/TLS en una <xref:System.Net.ServicePointManager> instancia de.</span><span class="sxs-lookup"><span data-stu-id="83664-119">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="83664-120">Los valores posibles son equivalentes a los valores de la <xref:System.Net.Security.EncryptionPolicy> enumeración.</span><span class="sxs-lookup"><span data-stu-id="83664-120">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="83664-121">El uso de <xref:System.Security.Authentication.CipherAlgorithmType.Null> es necesario cuando la Directiva de cifrado se establece en `NoEncryption` .</span><span class="sxs-lookup"><span data-stu-id="83664-121">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="83664-122">El valor predeterminado es `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="83664-122">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="83664-123">Especifica si los métodos POST deben esperar recibir una `100-continue` respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="83664-123">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="83664-124">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="83664-124">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="83664-125">Especifica si las conexiones controladas por el administrador de puntos de servicio usan el algoritmo de Nagle.</span><span class="sxs-lookup"><span data-stu-id="83664-125">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="83664-126">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="83664-126">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83664-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="83664-127">Child Elements</span></span>  

 <span data-ttu-id="83664-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="83664-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83664-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="83664-129">Parent Elements</span></span>  
  
|<span data-ttu-id="83664-130">**Element**</span><span class="sxs-lookup"><span data-stu-id="83664-130">**Element**</span></span>|<span data-ttu-id="83664-131">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="83664-131">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="83664-132">Configuración</span><span class="sxs-lookup"><span data-stu-id="83664-132">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="83664-133">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="83664-133">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83664-134">Observaciones</span><span class="sxs-lookup"><span data-stu-id="83664-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="83664-135">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="83664-135">Configuration Files</span></span>  

 <span data-ttu-id="83664-136">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="83664-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83664-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83664-137">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="83664-138">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="83664-138">Network Settings Schema</span></span>](index.md)
