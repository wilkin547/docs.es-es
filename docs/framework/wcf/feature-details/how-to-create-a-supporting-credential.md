---
title: "Cómo: Crear una credencial de apoyo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c140b96fab0227a1563c8c1a511053d8d1ab944
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-supporting-credential"></a><span data-ttu-id="9e520-102">Cómo: Crear una credencial de apoyo</span><span class="sxs-lookup"><span data-stu-id="9e520-102">How to: Create a Supporting Credential</span></span>
<span data-ttu-id="9e520-103">Es posible tener un esquema de seguridad personalizado que requiera más de una credencial.</span><span class="sxs-lookup"><span data-stu-id="9e520-103">It is possible to have a custom security scheme that requires more than one credential.</span></span> <span data-ttu-id="9e520-104">Por ejemplo, un servicio puede solicitar del cliente un nombre de usuario y contraseña, pero también una credencial que demuestre que el cliente tiene más de 18 años.</span><span class="sxs-lookup"><span data-stu-id="9e520-104">For example, a service may demand from the client not just a user name and password, but also a credential that proves the client is over the age of 18.</span></span> <span data-ttu-id="9e520-105">La segunda credencial es un *credencial de apoyo*.</span><span class="sxs-lookup"><span data-stu-id="9e520-105">The second credential is a *supporting credential*.</span></span> <span data-ttu-id="9e520-106">En este tema, se explica cómo implementar dichos credenciales en un cliente [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e520-106">This topic explains how to implement such credentials in an [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e520-107">La especificación para admitir las credenciales forma parte de la especificación WS-SecurityPolicy.</span><span class="sxs-lookup"><span data-stu-id="9e520-107">The specification for supporting credentials is part of the WS-SecurityPolicy specification.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="9e520-108">[Especificaciones de seguridad de servicios web](http://go.microsoft.com/fwlink/?LinkId=88537).</span><span class="sxs-lookup"><span data-stu-id="9e520-108"> [Web Services Security Specifications](http://go.microsoft.com/fwlink/?LinkId=88537).</span></span>  
  
## <a name="supporting-tokens"></a><span data-ttu-id="9e520-109">Tokens auxiliares</span><span class="sxs-lookup"><span data-stu-id="9e520-109">Supporting Tokens</span></span>  
 <span data-ttu-id="9e520-110">En pocas palabras, cuando se usa seguridad de los mensajes, un *credenciales primarias* siempre se utiliza para proteger el mensaje (por ejemplo, un certificado X.509 o un vale de Kerberos).</span><span class="sxs-lookup"><span data-stu-id="9e520-110">In brief, when you use message security, a *primary credential* is always used to secure the message (for example, an X.509 certificate or a Kerberos ticket).</span></span>  
  
 <span data-ttu-id="9e520-111">Tal como se define en la especificación, un enlace de seguridad utiliza *tokens* para proteger el intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="9e520-111">As defined by the specification, a security binding uses *tokens* to secure the message exchange.</span></span> <span data-ttu-id="9e520-112">A *token* es una representación de una credencial de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9e520-112">A *token* is a representation of a security credential.</span></span>  
  
 <span data-ttu-id="9e520-113">El enlace de seguridad utiliza un token primario identificado en la directiva de enlace de seguridad para crear una firma.</span><span class="sxs-lookup"><span data-stu-id="9e520-113">The security binding uses a primary token identified in the security binding policy to create a signature.</span></span> <span data-ttu-id="9e520-114">Esta firma se conoce como el *firma del mensaje*.</span><span class="sxs-lookup"><span data-stu-id="9e520-114">This signature is referred to as the *message signature*.</span></span>  
  
 <span data-ttu-id="9e520-115">Los tokens adicionales se pueden especificar para aumentar las notificaciones proporcionadas por el token asociado a la firma del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9e520-115">Additional tokens can be specified to augment the claims provided by the token associated with the message signature.</span></span>  
  
## <a name="endorsing-signing-and-encrypting"></a><span data-ttu-id="9e520-116">Endosar, firmar y cifrar</span><span class="sxs-lookup"><span data-stu-id="9e520-116">Endorsing, Signing, and Encrypting</span></span>  
 <span data-ttu-id="9e520-117">Una credencial de soporte da como resultado un *token auxiliar* transmitido dentro del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9e520-117">A supporting credential results in a *supporting token* transmitted inside the message.</span></span> <span data-ttu-id="9e520-118">La especificación de WS-SecurityPolicy define cuatro maneras de adjuntar un token de aprobación al mensaje, tal y como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9e520-118">The WS-SecurityPolicy specification defines four ways to attach a supporting token to the message, as described in the following table.</span></span>  
  
|<span data-ttu-id="9e520-119">Finalidad</span><span class="sxs-lookup"><span data-stu-id="9e520-119">Purpose</span></span>|<span data-ttu-id="9e520-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e520-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e520-121">Firmado</span><span class="sxs-lookup"><span data-stu-id="9e520-121">Signed</span></span>|<span data-ttu-id="9e520-122">El token de aprobación está incluido en el encabezado de seguridad y es firmado por la firma del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9e520-122">The supporting token is included in the security header and is signed by the message signature.</span></span>|  
|<span data-ttu-id="9e520-123">Endosar</span><span class="sxs-lookup"><span data-stu-id="9e520-123">Endorsing</span></span>|<span data-ttu-id="9e520-124">Un *token de aprobación* firma la firma del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9e520-124">An *endorsing token* signs the message signature.</span></span>|  
|<span data-ttu-id="9e520-125">Firmar y endosar</span><span class="sxs-lookup"><span data-stu-id="9e520-125">Signed and Endorsing</span></span>|<span data-ttu-id="9e520-126">Los tokens firmados y endosados firman el elemento `ds:Signature` completo generado a partir de la firma del mensaje y están firmados por esa firma del mensaje; es decir, ambos tokens (el token utilizado para la firma del mensaje y el token endosado y firmado) se firman entre sí.</span><span class="sxs-lookup"><span data-stu-id="9e520-126">Signed, endorsing tokens sign the entire `ds:Signature` element produced from the message signature and are themselves signed by that message signature; that is, both tokens (the token used for the message signature and the signed endorsing token) sign each other.</span></span>|  
|<span data-ttu-id="9e520-127">Firmar y cifrar</span><span class="sxs-lookup"><span data-stu-id="9e520-127">Signed and Encrypting</span></span>|<span data-ttu-id="9e520-128">Los tokens de aprobación firmados y cifrados son tokens de aprobación firmados que también se cifran cuando aparecen en `wsse:SecurityHeader`.</span><span class="sxs-lookup"><span data-stu-id="9e520-128">Signed, encrypted supporting tokens are signed supporting tokens that are also encrypted when they appear in the `wsse:SecurityHeader`.</span></span>|  
  
## <a name="programming-supporting-credentials"></a><span data-ttu-id="9e520-129">Programar credenciales de aprobación</span><span class="sxs-lookup"><span data-stu-id="9e520-129">Programming Supporting Credentials</span></span>  
 <span data-ttu-id="9e520-130">Para crear un servicio que utiliza los tokens auxiliares debe crear un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="9e520-130">To create a service that uses supporting tokens you must create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span> <span data-ttu-id="9e520-131">([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Cómo: crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).)</span><span class="sxs-lookup"><span data-stu-id="9e520-131">([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).)</span></span>  
  
 <span data-ttu-id="9e520-132">El primer paso cuando se crea un enlace personalizado es crear un elemento de enlace de seguridad, que puede ser uno de tres tipos:</span><span class="sxs-lookup"><span data-stu-id="9e520-132">The first step when creating a custom binding is to create a security binding element, which can be one of three types:</span></span>  
  
-   <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="9e520-133">Todas las clases heredan del <xref:System.ServiceModel.Channels.SecurityBindingElement>, que incluye cuatro propiedades pertinentes:</span><span class="sxs-lookup"><span data-stu-id="9e520-133">All classes inherit from the <xref:System.ServiceModel.Channels.SecurityBindingElement>, which includes four relevant properties:</span></span>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### <a name="scopes"></a><span data-ttu-id="9e520-134">Ámbitos</span><span class="sxs-lookup"><span data-stu-id="9e520-134">Scopes</span></span>  
 <span data-ttu-id="9e520-135">Existen dos ámbitos para admitir las credenciales:</span><span class="sxs-lookup"><span data-stu-id="9e520-135">Two scopes exist for supporting credentials:</span></span>  
  
-   <span data-ttu-id="9e520-136">*Punto de conexión de los tokens auxiliares* admiten todas las operaciones de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9e520-136">*Endpoint supporting tokens* support all operations of an endpoint.</span></span> <span data-ttu-id="9e520-137">Es decir, se puede utilizar la credencial que el token de aprobación representa siempre que se invoca una operación de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9e520-137">That is, the credential that the supporting token represents can be used whenever any endpoint operations are invoked.</span></span>  
  
-   <span data-ttu-id="9e520-138">*Los tokens auxiliares de operación* admiten solo una operación de punto de conexión concreto.</span><span class="sxs-lookup"><span data-stu-id="9e520-138">*Operation supporting tokens* support only a specific endpoint operation.</span></span>  
  
 <span data-ttu-id="9e520-139">Tal y como han indicado los nombres de la propiedad, se puede requerir las credenciales de aprobación o estas pueden ser opcionales.</span><span class="sxs-lookup"><span data-stu-id="9e520-139">As indicated by the property names, supporting credentials can be either required or optional.</span></span> <span data-ttu-id="9e520-140">Es decir, si la credencial de aprobación se utiliza si está presente, aunque no es necesario, pero no se producirá un error en la autenticación si no está presente.</span><span class="sxs-lookup"><span data-stu-id="9e520-140">That is, if the supporting credential is used if it is present, although it is not necessary, but the authentication will not fail if it is not present.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="9e520-141">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="9e520-141">Procedures</span></span>  
  
#### <a name="to-create-a-custom-binding-that-includes-supporting-credentials"></a><span data-ttu-id="9e520-142">Para crear un enlace personalizado que incluye credenciales de aprobación</span><span class="sxs-lookup"><span data-stu-id="9e520-142">To create a custom binding that includes supporting credentials</span></span>  
  
1.  <span data-ttu-id="9e520-143">Crear un elemento de enlace de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9e520-143">Create a security binding element.</span></span> <span data-ttu-id="9e520-144">El ejemplo siguiente crea <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> con el modo de autenticación `UserNameForCertificate`.</span><span class="sxs-lookup"><span data-stu-id="9e520-144">The example below creates a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> with the `UserNameForCertificate` authentication mode.</span></span> <span data-ttu-id="9e520-145">Utilice el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="9e520-145">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A> method.</span></span>  
  
2.  <span data-ttu-id="9e520-146">Agregue el parámetro de aprobación a la colección de tipos devuelta por la propiedad adecuada (`Endorsing`, `Signed`, `SignedEncrypted`o `SignedEndorsed`).</span><span class="sxs-lookup"><span data-stu-id="9e520-146">Add the supporting parameter to the collection of types returned by the appropriate property (`Endorsing`, `Signed`, `SignedEncrypted`, or `SignedEndorsed`).</span></span> <span data-ttu-id="9e520-147">Los tipos en el espacio de nombres <xref:System.ServiceModel.Security.Tokens> incluyen tipos utilizados normalmente, como <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="9e520-147">The types in the <xref:System.ServiceModel.Security.Tokens> namespace include commonly used types, such as the <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e520-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e520-148">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9e520-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e520-149">Description</span></span>  
 <span data-ttu-id="9e520-150">En el ejemplo siguiente se crea una instancia de<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y agrega una instancia de la clase <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> a la colección que ha devuelto la propiedad endosada.</span><span class="sxs-lookup"><span data-stu-id="9e520-150">The following example creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and adds an instance of the <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> class to the collection the Endorsing property returned.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9e520-151">Código</span><span class="sxs-lookup"><span data-stu-id="9e520-151">Code</span></span>  
 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="9e520-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e520-152">See Also</span></span>  
 [<span data-ttu-id="9e520-153">Cómo: crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9e520-153">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
