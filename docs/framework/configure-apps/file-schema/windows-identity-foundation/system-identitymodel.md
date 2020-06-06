---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: a54f5ce86aee1a5e831c0b10aa1471d4a82f40a5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251790"
---
# \<system.identityModel>
<span data-ttu-id="9bf3d-102">Proporciona la configuración para habilitar las opciones de Windows Identity Foundation (WIF) en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9bf3d-102">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel>**  
  
## <a name="syntax"></a><span data-ttu-id="9bf3d-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9bf3d-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9bf3d-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9bf3d-104">Attributes and Elements</span></span>  
 <span data-ttu-id="9bf3d-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9bf3d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9bf3d-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="9bf3d-106">Attributes</span></span>  
 <span data-ttu-id="9bf3d-107">None</span><span class="sxs-lookup"><span data-stu-id="9bf3d-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9bf3d-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9bf3d-108">Child Elements</span></span>  
  
|<span data-ttu-id="9bf3d-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="9bf3d-109">Element</span></span>|<span data-ttu-id="9bf3d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bf3d-110">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="9bf3d-111">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="9bf3d-111">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9bf3d-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9bf3d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="9bf3d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="9bf3d-113">Element</span></span>|<span data-ttu-id="9bf3d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bf3d-114">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="9bf3d-115">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9bf3d-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bf3d-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9bf3d-116">Remarks</span></span>  
 <span data-ttu-id="9bf3d-117">Agregue una `<system.identityModel>` sección al archivo de configuración para configurar un servicio o una aplicación para usar Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="9bf3d-117">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="9bf3d-118">El `<system.identityModel>` elemento se representa mediante la <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> clase.</span><span class="sxs-lookup"><span data-stu-id="9bf3d-118">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bf3d-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9bf3d-119">Example</span></span>  
 <span data-ttu-id="9bf3d-120">En el ejemplo siguiente se muestra cómo agregar una `<system.identityModel>` sección a un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="9bf3d-120">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="9bf3d-121">Primero debe agregar la sección de configuración y la declaración de espacio de nombres en el `<configSections>` elemento.</span><span class="sxs-lookup"><span data-stu-id="9bf3d-121">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="9bf3d-122">Después, puede Agregar el `<system.IdentityModel>` elemento al archivo de configuración para especificar una o más configuraciones de identidad.</span><span class="sxs-lookup"><span data-stu-id="9bf3d-122">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9bf3d-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9bf3d-123">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
