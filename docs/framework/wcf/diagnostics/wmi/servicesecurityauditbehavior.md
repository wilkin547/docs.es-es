---
description: 'Más información acerca de: ServiceSecurityAuditBehavior'
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 5dfb3a70a80d5dea1ed360dcaf3a0db989bf671b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715475"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="ccca2-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="ccca2-103">ServiceSecurityAuditBehavior</span></span>

<span data-ttu-id="ccca2-104">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="ccca2-104">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccca2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccca2-105">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ccca2-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="ccca2-106">Methods</span></span>  

 <span data-ttu-id="ccca2-107">La clase ServiceSecurityAuditBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="ccca2-107">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ccca2-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ccca2-108">Properties</span></span>  

 <span data-ttu-id="ccca2-109">La clase ServiceSecurityAuditBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="ccca2-109">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="ccca2-110">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="ccca2-110">AuditLogLocation</span></span>  

 <span data-ttu-id="ccca2-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ccca2-111">Data type: string</span></span>  
  
 <span data-ttu-id="ccca2-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ccca2-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ccca2-113">La ubicación del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="ccca2-113">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="ccca2-114">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="ccca2-114">MessageAuthenticationAuditLevel</span></span>  

 <span data-ttu-id="ccca2-115">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ccca2-115">Data type: string</span></span>  
  
 <span data-ttu-id="ccca2-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ccca2-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ccca2-117">El tipo de nivel de autenticación de mensajes que se usa para registrar eventos de auditoría.</span><span class="sxs-lookup"><span data-stu-id="ccca2-117">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="ccca2-118">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="ccca2-118">ServiceAuthorizationAuditLevel</span></span>  

 <span data-ttu-id="ccca2-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ccca2-119">Data type: string</span></span>  
  
 <span data-ttu-id="ccca2-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ccca2-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ccca2-121">Los tipos de eventos de autorización que se graban en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="ccca2-121">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="ccca2-122">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="ccca2-122">SuppressAuditFailure</span></span>  

 <span data-ttu-id="ccca2-123">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="ccca2-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="ccca2-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ccca2-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ccca2-125">Un valor booleano que especifica el comportamiento para suprimir errores al escribir en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="ccca2-125">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccca2-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccca2-126">Requirements</span></span>  
  
|<span data-ttu-id="ccca2-127">MOF</span><span class="sxs-lookup"><span data-stu-id="ccca2-127">MOF</span></span>|<span data-ttu-id="ccca2-128">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ccca2-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ccca2-129">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ccca2-129">Namespace</span></span>|<span data-ttu-id="ccca2-130">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ccca2-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ccca2-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccca2-131">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
