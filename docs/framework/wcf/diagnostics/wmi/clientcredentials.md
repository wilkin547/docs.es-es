---
description: 'Más información acerca de: ClientCredentials'
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: 7b0b5a05e5b61de717567de664079f2ed1e20f6b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757668"
---
# <a name="clientcredentials"></a><span data-ttu-id="7b3c9-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="7b3c9-103">ClientCredentials</span></span>

<span data-ttu-id="7b3c9-104">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="7b3c9-104">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b3c9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b3c9-105">Syntax</span></span>  
  
```csharp
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7b3c9-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="7b3c9-106">Methods</span></span>  

 <span data-ttu-id="7b3c9-107">La clase ClientCredentials no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="7b3c9-107">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7b3c9-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7b3c9-108">Properties</span></span>  

 <span data-ttu-id="7b3c9-109">La clase ClientCredentials tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="7b3c9-109">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="7b3c9-110">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="7b3c9-110">ClientCertificate</span></span>  

 <span data-ttu-id="7b3c9-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="7b3c9-111">Data type: string</span></span>  
  
 <span data-ttu-id="7b3c9-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="7b3c9-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b3c9-113">El certificado X.509 que utiliza el cliente para autenticarse en el servicio.</span><span class="sxs-lookup"><span data-stu-id="7b3c9-113">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="7b3c9-114">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="7b3c9-114">HttpDigest</span></span>  

 <span data-ttu-id="7b3c9-115">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="7b3c9-115">Data type: string</span></span>  
  
 <span data-ttu-id="7b3c9-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="7b3c9-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b3c9-117">La credencial de resumen Http Digest actual.</span><span class="sxs-lookup"><span data-stu-id="7b3c9-117">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="7b3c9-118">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="7b3c9-118">IssuedToken</span></span>  

 <span data-ttu-id="7b3c9-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="7b3c9-119">Data type: string</span></span>  
  
 <span data-ttu-id="7b3c9-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="7b3c9-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b3c9-121">La dirección y el enlace del extremo utilizados para contactar con el servicio de tokens de seguridad local.</span><span class="sxs-lookup"><span data-stu-id="7b3c9-121">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="7b3c9-122">Del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="7b3c9-122">Peer</span></span>  

 <span data-ttu-id="7b3c9-123">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="7b3c9-123">Data type: string</span></span>  
  
 <span data-ttu-id="7b3c9-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="7b3c9-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b3c9-125">Las credenciales que el nodo del mismo nivel utiliza para autenticarse a otros nodos de la malla.</span><span class="sxs-lookup"><span data-stu-id="7b3c9-125">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="7b3c9-126">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="7b3c9-126">ServiceCertificate</span></span>  

 <span data-ttu-id="7b3c9-127">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="7b3c9-127">Data type: string</span></span>  
  
 <span data-ttu-id="7b3c9-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="7b3c9-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b3c9-129">El certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="7b3c9-129">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="7b3c9-130">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="7b3c9-130">SupportInteractive</span></span>  

 <span data-ttu-id="7b3c9-131">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="7b3c9-131">Data type: boolean</span></span>  
  
 <span data-ttu-id="7b3c9-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="7b3c9-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b3c9-133">Un valor booleano que especifica si la credencial admite negociación interactiva.</span><span class="sxs-lookup"><span data-stu-id="7b3c9-133">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="7b3c9-134">UserName</span><span class="sxs-lookup"><span data-stu-id="7b3c9-134">UserName</span></span>  

 <span data-ttu-id="7b3c9-135">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="7b3c9-135">Data type: string</span></span>  
  
 <span data-ttu-id="7b3c9-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="7b3c9-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b3c9-137">El nombre de usuario y la contraseña que el cliente utiliza para autenticarse al servicio.</span><span class="sxs-lookup"><span data-stu-id="7b3c9-137">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="7b3c9-138">Windows</span><span class="sxs-lookup"><span data-stu-id="7b3c9-138">Windows</span></span>  

 <span data-ttu-id="7b3c9-139">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="7b3c9-139">Data type: string</span></span>  
  
 <span data-ttu-id="7b3c9-140">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="7b3c9-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b3c9-141">Las credenciales de Windows que el cliente utiliza para autenticarse al servicio.</span><span class="sxs-lookup"><span data-stu-id="7b3c9-141">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b3c9-142">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b3c9-142">Requirements</span></span>  
  
|<span data-ttu-id="7b3c9-143">MOF</span><span class="sxs-lookup"><span data-stu-id="7b3c9-143">MOF</span></span>|<span data-ttu-id="7b3c9-144">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7b3c9-144">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7b3c9-145">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="7b3c9-145">Namespace</span></span>|<span data-ttu-id="7b3c9-146">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7b3c9-146">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b3c9-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b3c9-147">See also</span></span>

- <xref:System.ServiceModel.Description.ClientCredentials>
