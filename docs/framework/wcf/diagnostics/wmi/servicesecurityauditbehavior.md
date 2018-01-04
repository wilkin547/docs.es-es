---
title: ServiceSecurityAuditBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ea9c04c201ff022fcea54b81a998b7020fb2a836
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="a363d-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="a363d-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="a363d-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="a363d-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a363d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a363d-104">Syntax</span></span>  
  
```  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a363d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a363d-105">Methods</span></span>  
 <span data-ttu-id="a363d-106">La clase ServiceSecurityAuditBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="a363d-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a363d-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a363d-107">Properties</span></span>  
 <span data-ttu-id="a363d-108">La clase ServiceSecurityAuditBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="a363d-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="a363d-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="a363d-109">AuditLogLocation</span></span>  
 <span data-ttu-id="a363d-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="a363d-110">Data type: string</span></span>  
  
 <span data-ttu-id="a363d-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a363d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a363d-112">La ubicación del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="a363d-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="a363d-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="a363d-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="a363d-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="a363d-114">Data type: string</span></span>  
  
 <span data-ttu-id="a363d-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a363d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a363d-116">El tipo de nivel de autenticación de mensajes que se usa para registrar eventos de auditoría.</span><span class="sxs-lookup"><span data-stu-id="a363d-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="a363d-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="a363d-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="a363d-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="a363d-118">Data type: string</span></span>  
  
 <span data-ttu-id="a363d-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a363d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a363d-120">Los tipos de eventos de autorización que se graban en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="a363d-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="a363d-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="a363d-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="a363d-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="a363d-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="a363d-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a363d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a363d-124">Un valor booleano que especifica el comportamiento para suprimir errores al escribir en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="a363d-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a363d-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a363d-125">Requirements</span></span>  
  
|<span data-ttu-id="a363d-126">MOF</span><span class="sxs-lookup"><span data-stu-id="a363d-126">MOF</span></span>|<span data-ttu-id="a363d-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a363d-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a363d-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a363d-128">Namespace</span></span>|<span data-ttu-id="a363d-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a363d-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a363d-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="a363d-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
