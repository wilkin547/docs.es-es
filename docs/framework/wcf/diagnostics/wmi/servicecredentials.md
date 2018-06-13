---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: bf906e09ae71d26f8e95877f1c545c0724d57b9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485769"
---
# <a name="servicecredentials"></a><span data-ttu-id="237ab-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="237ab-102">ServiceCredentials</span></span>
<span data-ttu-id="237ab-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="237ab-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="237ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="237ab-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="237ab-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="237ab-105">Methods</span></span>  
 <span data-ttu-id="237ab-106">La clase ServiceCredentials no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="237ab-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="237ab-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="237ab-107">Properties</span></span>  
 <span data-ttu-id="237ab-108">La clase ServiceCredentials posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="237ab-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="237ab-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="237ab-109">ClientCertificate</span></span>  
 <span data-ttu-id="237ab-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="237ab-110">Data type: string</span></span>  
  
 <span data-ttu-id="237ab-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="237ab-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="237ab-112">La autenticación del certificado de cliente y la configuración de aprovisionamiento para este servicio.</span><span class="sxs-lookup"><span data-stu-id="237ab-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="237ab-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="237ab-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="237ab-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="237ab-114">Data type: string</span></span>  
  
 <span data-ttu-id="237ab-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="237ab-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="237ab-116">Los valores actuales de autenticación de token emitido para este servicio.</span><span class="sxs-lookup"><span data-stu-id="237ab-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="237ab-117">Del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="237ab-117">Peer</span></span>  
 <span data-ttu-id="237ab-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="237ab-118">Data type: string</span></span>  
  
 <span data-ttu-id="237ab-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="237ab-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="237ab-120">La autenticación de la credencial actual y la configuración de aprovisionamiento que van a utilizar los extremos de transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="237ab-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="237ab-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="237ab-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="237ab-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="237ab-122">Data type: string</span></span>  
  
 <span data-ttu-id="237ab-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="237ab-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="237ab-124">Especifica los valores de conversación seguros actuales.</span><span class="sxs-lookup"><span data-stu-id="237ab-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="237ab-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="237ab-125">ServiceCertificate</span></span>  
 <span data-ttu-id="237ab-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="237ab-126">Data type: string</span></span>  
  
 <span data-ttu-id="237ab-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="237ab-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="237ab-128">El certificado asociado a este servicio.</span><span class="sxs-lookup"><span data-stu-id="237ab-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="237ab-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="237ab-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="237ab-130">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="237ab-130">Data type: string</span></span>  
  
 <span data-ttu-id="237ab-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="237ab-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="237ab-132">Los valores de nombre de usuario/contraseña para este servicio.</span><span class="sxs-lookup"><span data-stu-id="237ab-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="237ab-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="237ab-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="237ab-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="237ab-134">Data type: string</span></span>  
  
 <span data-ttu-id="237ab-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="237ab-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="237ab-136">Los valores de autenticación de Windows para este servicio.</span><span class="sxs-lookup"><span data-stu-id="237ab-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="237ab-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="237ab-137">Requirements</span></span>  
  
|<span data-ttu-id="237ab-138">MOF</span><span class="sxs-lookup"><span data-stu-id="237ab-138">MOF</span></span>|<span data-ttu-id="237ab-139">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="237ab-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="237ab-140">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="237ab-140">Namespace</span></span>|<span data-ttu-id="237ab-141">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="237ab-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="237ab-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="237ab-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>
