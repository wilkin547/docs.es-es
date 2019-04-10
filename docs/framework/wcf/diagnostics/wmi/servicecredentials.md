---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d9563bd3bfe067ad83bfa03e7c6375a9db933f14
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230933"
---
# <a name="servicecredentials"></a><span data-ttu-id="d96ae-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="d96ae-102">ServiceCredentials</span></span>
<span data-ttu-id="d96ae-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="d96ae-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d96ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d96ae-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="d96ae-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d96ae-105">Methods</span></span>  
 <span data-ttu-id="d96ae-106">La clase ServiceCredentials no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="d96ae-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d96ae-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d96ae-107">Properties</span></span>  
 <span data-ttu-id="d96ae-108">La clase ServiceCredentials posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d96ae-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="d96ae-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="d96ae-109">ClientCertificate</span></span>  
 <span data-ttu-id="d96ae-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d96ae-110">Data type: string</span></span>  
  
 <span data-ttu-id="d96ae-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="d96ae-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d96ae-112">La autenticación del certificado de cliente y la configuración de aprovisionamiento para este servicio.</span><span class="sxs-lookup"><span data-stu-id="d96ae-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="d96ae-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="d96ae-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="d96ae-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d96ae-114">Data type: string</span></span>  
  
 <span data-ttu-id="d96ae-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="d96ae-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d96ae-116">Los valores actuales de autenticación de token emitido para este servicio.</span><span class="sxs-lookup"><span data-stu-id="d96ae-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="d96ae-117">Del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="d96ae-117">Peer</span></span>  
 <span data-ttu-id="d96ae-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d96ae-118">Data type: string</span></span>  
  
 <span data-ttu-id="d96ae-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="d96ae-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d96ae-120">La autenticación de la credencial actual y la configuración de aprovisionamiento que van a utilizar los puntos de conexión de transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="d96ae-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="d96ae-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="d96ae-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="d96ae-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d96ae-122">Data type: string</span></span>  
  
 <span data-ttu-id="d96ae-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="d96ae-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d96ae-124">Especifica los valores de conversación seguros actuales.</span><span class="sxs-lookup"><span data-stu-id="d96ae-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="d96ae-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="d96ae-125">ServiceCertificate</span></span>  
 <span data-ttu-id="d96ae-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d96ae-126">Data type: string</span></span>  
  
 <span data-ttu-id="d96ae-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="d96ae-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d96ae-128">El certificado asociado a este servicio.</span><span class="sxs-lookup"><span data-stu-id="d96ae-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="d96ae-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="d96ae-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="d96ae-130">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d96ae-130">Data type: string</span></span>  
  
 <span data-ttu-id="d96ae-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="d96ae-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d96ae-132">Los valores de nombre de usuario/contraseña para este servicio.</span><span class="sxs-lookup"><span data-stu-id="d96ae-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="d96ae-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="d96ae-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="d96ae-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d96ae-134">Data type: string</span></span>  
  
 <span data-ttu-id="d96ae-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="d96ae-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d96ae-136">Los valores de autenticación de Windows para este servicio.</span><span class="sxs-lookup"><span data-stu-id="d96ae-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d96ae-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d96ae-137">Requirements</span></span>  
  
|<span data-ttu-id="d96ae-138">MOF</span><span class="sxs-lookup"><span data-stu-id="d96ae-138">MOF</span></span>|<span data-ttu-id="d96ae-139">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d96ae-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d96ae-140">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="d96ae-140">Namespace</span></span>|<span data-ttu-id="d96ae-141">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d96ae-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d96ae-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="d96ae-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>
