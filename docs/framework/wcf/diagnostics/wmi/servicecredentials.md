---
title: ServiceCredentials
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e4cc9d7d7d46157b7df202c6daffb31b90fa98c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="servicecredentials"></a><span data-ttu-id="1fc7d-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="1fc7d-102">ServiceCredentials</span></span>
<span data-ttu-id="1fc7d-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="1fc7d-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fc7d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1fc7d-104">Syntax</span></span>  
  
```  
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1fc7d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1fc7d-105">Methods</span></span>  
 <span data-ttu-id="1fc7d-106">La clase ServiceCredentials no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="1fc7d-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1fc7d-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1fc7d-107">Properties</span></span>  
 <span data-ttu-id="1fc7d-108">La clase ServiceCredentials posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1fc7d-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="1fc7d-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="1fc7d-109">ClientCertificate</span></span>  
 <span data-ttu-id="1fc7d-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1fc7d-110">Data type: string</span></span>  
  
 <span data-ttu-id="1fc7d-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1fc7d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fc7d-112">La autenticación del certificado de cliente y la configuración de aprovisionamiento para este servicio.</span><span class="sxs-lookup"><span data-stu-id="1fc7d-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="1fc7d-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="1fc7d-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="1fc7d-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1fc7d-114">Data type: string</span></span>  
  
 <span data-ttu-id="1fc7d-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1fc7d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fc7d-116">Los valores actuales de autenticación de token emitido para este servicio.</span><span class="sxs-lookup"><span data-stu-id="1fc7d-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="1fc7d-117">Del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="1fc7d-117">Peer</span></span>  
 <span data-ttu-id="1fc7d-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1fc7d-118">Data type: string</span></span>  
  
 <span data-ttu-id="1fc7d-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1fc7d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fc7d-120">La autenticación de la credencial actual y la configuración de aprovisionamiento que van a utilizar los extremos de transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="1fc7d-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="1fc7d-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="1fc7d-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="1fc7d-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1fc7d-122">Data type: string</span></span>  
  
 <span data-ttu-id="1fc7d-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1fc7d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fc7d-124">Especifica los valores de conversación seguros actuales.</span><span class="sxs-lookup"><span data-stu-id="1fc7d-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="1fc7d-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="1fc7d-125">ServiceCertificate</span></span>  
 <span data-ttu-id="1fc7d-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1fc7d-126">Data type: string</span></span>  
  
 <span data-ttu-id="1fc7d-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1fc7d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fc7d-128">El certificado asociado a este servicio.</span><span class="sxs-lookup"><span data-stu-id="1fc7d-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="1fc7d-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="1fc7d-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="1fc7d-130">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1fc7d-130">Data type: string</span></span>  
  
 <span data-ttu-id="1fc7d-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1fc7d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fc7d-132">Los valores de nombre de usuario/contraseña para este servicio.</span><span class="sxs-lookup"><span data-stu-id="1fc7d-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="1fc7d-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="1fc7d-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="1fc7d-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1fc7d-134">Data type: string</span></span>  
  
 <span data-ttu-id="1fc7d-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1fc7d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fc7d-136">Los valores de autenticación de Windows para este servicio.</span><span class="sxs-lookup"><span data-stu-id="1fc7d-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fc7d-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1fc7d-137">Requirements</span></span>  
  
|<span data-ttu-id="1fc7d-138">MOF</span><span class="sxs-lookup"><span data-stu-id="1fc7d-138">MOF</span></span>|<span data-ttu-id="1fc7d-139">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1fc7d-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1fc7d-140">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="1fc7d-140">Namespace</span></span>|<span data-ttu-id="1fc7d-141">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1fc7d-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1fc7d-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fc7d-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>
