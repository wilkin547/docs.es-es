---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: dc48b8742c60714720be3cf4b22ba672f73c720a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570231"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="64c57-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="64c57-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="64c57-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="64c57-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64c57-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64c57-104">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="64c57-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="64c57-105">Methods</span></span>  
 <span data-ttu-id="64c57-106">La clase ServiceSecurityAuditBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="64c57-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="64c57-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="64c57-107">Properties</span></span>  
 <span data-ttu-id="64c57-108">La clase ServiceSecurityAuditBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="64c57-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="64c57-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="64c57-109">AuditLogLocation</span></span>  
 <span data-ttu-id="64c57-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="64c57-110">Data type: string</span></span>  
  
 <span data-ttu-id="64c57-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="64c57-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64c57-112">La ubicación del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="64c57-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="64c57-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="64c57-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="64c57-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="64c57-114">Data type: string</span></span>  
  
 <span data-ttu-id="64c57-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="64c57-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64c57-116">El tipo de nivel de autenticación de mensajes que se usa para registrar eventos de auditoría.</span><span class="sxs-lookup"><span data-stu-id="64c57-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="64c57-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="64c57-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="64c57-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="64c57-118">Data type: string</span></span>  
  
 <span data-ttu-id="64c57-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="64c57-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64c57-120">Los tipos de eventos de autorización que se graban en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="64c57-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="64c57-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="64c57-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="64c57-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="64c57-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="64c57-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="64c57-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64c57-124">Un valor booleano que especifica el comportamiento para suprimir errores al escribir en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="64c57-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64c57-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64c57-125">Requirements</span></span>  
  
|<span data-ttu-id="64c57-126">MOF</span><span class="sxs-lookup"><span data-stu-id="64c57-126">MOF</span></span>|<span data-ttu-id="64c57-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="64c57-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="64c57-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="64c57-128">Namespace</span></span>|<span data-ttu-id="64c57-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="64c57-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64c57-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="64c57-130">See also</span></span>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
