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
ms.openlocfilehash: 1ce712bbdb258c477a2ee56f47281b1a1d09ec54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="6265f-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="6265f-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="6265f-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="6265f-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6265f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6265f-104">Syntax</span></span>  
  
```  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6265f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6265f-105">Methods</span></span>  
 <span data-ttu-id="6265f-106">La clase ServiceSecurityAuditBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="6265f-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6265f-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6265f-107">Properties</span></span>  
 <span data-ttu-id="6265f-108">La clase ServiceSecurityAuditBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="6265f-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="6265f-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="6265f-109">AuditLogLocation</span></span>  
 <span data-ttu-id="6265f-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6265f-110">Data type: string</span></span>  
  
 <span data-ttu-id="6265f-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6265f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6265f-112">La ubicación del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="6265f-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="6265f-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="6265f-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="6265f-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6265f-114">Data type: string</span></span>  
  
 <span data-ttu-id="6265f-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6265f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6265f-116">El tipo de nivel de autenticación de mensajes que se usa para registrar eventos de auditoría.</span><span class="sxs-lookup"><span data-stu-id="6265f-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="6265f-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="6265f-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="6265f-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6265f-118">Data type: string</span></span>  
  
 <span data-ttu-id="6265f-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6265f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6265f-120">Los tipos de eventos de autorización que se graban en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="6265f-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="6265f-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="6265f-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="6265f-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="6265f-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="6265f-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6265f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6265f-124">Un valor booleano que especifica el comportamiento para suprimir errores al escribir en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="6265f-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6265f-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6265f-125">Requirements</span></span>  
  
|<span data-ttu-id="6265f-126">MOF</span><span class="sxs-lookup"><span data-stu-id="6265f-126">MOF</span></span>|<span data-ttu-id="6265f-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6265f-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6265f-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6265f-128">Namespace</span></span>|<span data-ttu-id="6265f-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6265f-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6265f-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="6265f-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
