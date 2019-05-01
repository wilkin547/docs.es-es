---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 30679e1f67c6943bf674a6bbd8bf12be090765a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956902"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="61834-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="61834-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="61834-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="61834-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61834-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61834-104">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="61834-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="61834-105">Methods</span></span>  
 <span data-ttu-id="61834-106">La clase ServiceSecurityAuditBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="61834-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="61834-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="61834-107">Properties</span></span>  
 <span data-ttu-id="61834-108">La clase ServiceSecurityAuditBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="61834-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="61834-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="61834-109">AuditLogLocation</span></span>  
 <span data-ttu-id="61834-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="61834-110">Data type: string</span></span>  
  
 <span data-ttu-id="61834-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="61834-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61834-112">La ubicación del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="61834-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="61834-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="61834-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="61834-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="61834-114">Data type: string</span></span>  
  
 <span data-ttu-id="61834-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="61834-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61834-116">El tipo de nivel de autenticación de mensajes que se usa para registrar eventos de auditoría.</span><span class="sxs-lookup"><span data-stu-id="61834-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="61834-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="61834-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="61834-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="61834-118">Data type: string</span></span>  
  
 <span data-ttu-id="61834-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="61834-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61834-120">Los tipos de eventos de autorización que se graban en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="61834-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="61834-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="61834-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="61834-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="61834-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="61834-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="61834-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61834-124">Un valor booleano que especifica el comportamiento para suprimir errores al escribir en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="61834-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61834-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="61834-125">Requirements</span></span>  
  
|<span data-ttu-id="61834-126">MOF</span><span class="sxs-lookup"><span data-stu-id="61834-126">MOF</span></span>|<span data-ttu-id="61834-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="61834-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="61834-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="61834-128">Namespace</span></span>|<span data-ttu-id="61834-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="61834-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61834-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="61834-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
