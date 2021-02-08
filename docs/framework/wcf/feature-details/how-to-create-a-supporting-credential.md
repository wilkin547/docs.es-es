---
description: 'Más información acerca de cómo: crear una credencial de soporte técnico'
title: Procedimiento para crear una credencial de apoyo
ms.date: 03/30/2017
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
ms.openlocfilehash: 2f84e58eb0b8df5e1297fcbc50ddcac96db4fe5c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793823"
---
# <a name="how-to-create-a-supporting-credential"></a><span data-ttu-id="800dd-103">Procedimiento para crear una credencial de apoyo</span><span class="sxs-lookup"><span data-stu-id="800dd-103">How to: Create a Supporting Credential</span></span>

<span data-ttu-id="800dd-104">Es posible tener un esquema de seguridad personalizado que requiera más de una credencial.</span><span class="sxs-lookup"><span data-stu-id="800dd-104">It is possible to have a custom security scheme that requires more than one credential.</span></span> <span data-ttu-id="800dd-105">Por ejemplo, un servicio puede solicitar del cliente un nombre de usuario y contraseña, pero también una credencial que demuestre que el cliente tiene más de 18 años.</span><span class="sxs-lookup"><span data-stu-id="800dd-105">For example, a service may demand from the client not just a user name and password, but also a credential that proves the client is over the age of 18.</span></span> <span data-ttu-id="800dd-106">La segunda credencial es una *credencial de apoyo*.</span><span class="sxs-lookup"><span data-stu-id="800dd-106">The second credential is a *supporting credential*.</span></span> <span data-ttu-id="800dd-107">En este tema se explica cómo implementar estas credenciales en un cliente de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="800dd-107">This topic explains how to implement such credentials in an Windows Communication Foundation (WCF) client.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="800dd-108">La especificación para admitir las credenciales forma parte de la especificación WS-SecurityPolicy.</span><span class="sxs-lookup"><span data-stu-id="800dd-108">The specification for supporting credentials is part of the WS-SecurityPolicy specification.</span></span> <span data-ttu-id="800dd-109">Para obtener más información, vea [Especificaciones de seguridad de servicios web](/previous-versions/dotnet/articles/ms951273(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="800dd-109">For more information, see [Web Services Security Specifications](/previous-versions/dotnet/articles/ms951273(v=msdn.10)).</span></span>  
  
## <a name="supporting-tokens"></a><span data-ttu-id="800dd-110">Tokens auxiliares</span><span class="sxs-lookup"><span data-stu-id="800dd-110">Supporting Tokens</span></span>  

 <span data-ttu-id="800dd-111">En Resumen, cuando se usa la seguridad de mensajes, siempre se usa una *credencial principal* para proteger el mensaje (por ejemplo, un certificado X. 509 o un vale de Kerberos).</span><span class="sxs-lookup"><span data-stu-id="800dd-111">In brief, when you use message security, a *primary credential* is always used to secure the message (for example, an X.509 certificate or a Kerberos ticket).</span></span>  
  
 <span data-ttu-id="800dd-112">Tal y como se define en la especificación, un enlace de seguridad utiliza *tokens* para proteger el intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="800dd-112">As defined by the specification, a security binding uses *tokens* to secure the message exchange.</span></span> <span data-ttu-id="800dd-113">Un *token* es una representación de una credencial de seguridad.</span><span class="sxs-lookup"><span data-stu-id="800dd-113">A *token* is a representation of a security credential.</span></span>  
  
 <span data-ttu-id="800dd-114">El enlace de seguridad utiliza un token primario identificado en la directiva de enlace de seguridad para crear una firma.</span><span class="sxs-lookup"><span data-stu-id="800dd-114">The security binding uses a primary token identified in the security binding policy to create a signature.</span></span> <span data-ttu-id="800dd-115">Esta firma se conoce como la *firma del mensaje*.</span><span class="sxs-lookup"><span data-stu-id="800dd-115">This signature is referred to as the *message signature*.</span></span>  
  
 <span data-ttu-id="800dd-116">Los tokens adicionales se pueden especificar para aumentar las notificaciones proporcionadas por el token asociado a la firma del mensaje.</span><span class="sxs-lookup"><span data-stu-id="800dd-116">Additional tokens can be specified to augment the claims provided by the token associated with the message signature.</span></span>  
  
## <a name="endorsing-signing-and-encrypting"></a><span data-ttu-id="800dd-117">Endosar, firmar y cifrar</span><span class="sxs-lookup"><span data-stu-id="800dd-117">Endorsing, Signing, and Encrypting</span></span>  

 <span data-ttu-id="800dd-118">Una credencial de apoyo da como resultado un *token auxiliar* que se transmite dentro del mensaje.</span><span class="sxs-lookup"><span data-stu-id="800dd-118">A supporting credential results in a *supporting token* transmitted inside the message.</span></span> <span data-ttu-id="800dd-119">La especificación de WS-SecurityPolicy define cuatro maneras de adjuntar un token de aprobación al mensaje, tal y como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="800dd-119">The WS-SecurityPolicy specification defines four ways to attach a supporting token to the message, as described in the following table.</span></span>  
  
|<span data-ttu-id="800dd-120">Propósito</span><span class="sxs-lookup"><span data-stu-id="800dd-120">Purpose</span></span>|<span data-ttu-id="800dd-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="800dd-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="800dd-122">Firmado</span><span class="sxs-lookup"><span data-stu-id="800dd-122">Signed</span></span>|<span data-ttu-id="800dd-123">El token de aprobación está incluido en el encabezado de seguridad y es firmado por la firma del mensaje.</span><span class="sxs-lookup"><span data-stu-id="800dd-123">The supporting token is included in the security header and is signed by the message signature.</span></span>|  
|<span data-ttu-id="800dd-124">Endosar</span><span class="sxs-lookup"><span data-stu-id="800dd-124">Endorsing</span></span>|<span data-ttu-id="800dd-125">Un *token* de aprobación firma la firma del mensaje.</span><span class="sxs-lookup"><span data-stu-id="800dd-125">An *endorsing token* signs the message signature.</span></span>|  
|<span data-ttu-id="800dd-126">Firmar y endosar</span><span class="sxs-lookup"><span data-stu-id="800dd-126">Signed and Endorsing</span></span>|<span data-ttu-id="800dd-127">Los tokens firmados y endosados firman el elemento `ds:Signature` completo generado a partir de la firma del mensaje y están firmados por esa firma del mensaje; es decir, ambos tokens (el token utilizado para la firma del mensaje y el token endosado y firmado) se firman entre sí.</span><span class="sxs-lookup"><span data-stu-id="800dd-127">Signed, endorsing tokens sign the entire `ds:Signature` element produced from the message signature and are themselves signed by that message signature; that is, both tokens (the token used for the message signature and the signed endorsing token) sign each other.</span></span>|  
|<span data-ttu-id="800dd-128">Firmar y cifrar</span><span class="sxs-lookup"><span data-stu-id="800dd-128">Signed and Encrypting</span></span>|<span data-ttu-id="800dd-129">Los tokens de aprobación firmados y cifrados son tokens de aprobación firmados que también se cifran cuando aparecen en `wsse:SecurityHeader`.</span><span class="sxs-lookup"><span data-stu-id="800dd-129">Signed, encrypted supporting tokens are signed supporting tokens that are also encrypted when they appear in the `wsse:SecurityHeader`.</span></span>|  
  
## <a name="programming-supporting-credentials"></a><span data-ttu-id="800dd-130">Programar credenciales de aprobación</span><span class="sxs-lookup"><span data-stu-id="800dd-130">Programming Supporting Credentials</span></span>  

 <span data-ttu-id="800dd-131">Para crear un servicio que use tokens auxiliares, debe crear un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="800dd-131">To create a service that uses supporting tokens you must create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span></span> <span data-ttu-id="800dd-132">(Para obtener más información, consulte [Cómo: crear un enlace personalizado mediante SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)).</span><span class="sxs-lookup"><span data-stu-id="800dd-132">(For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).)</span></span>  
  
 <span data-ttu-id="800dd-133">El primer paso cuando se crea un enlace personalizado es crear un elemento de enlace de seguridad, que puede ser uno de tres tipos:</span><span class="sxs-lookup"><span data-stu-id="800dd-133">The first step when creating a custom binding is to create a security binding element, which can be one of three types:</span></span>  
  
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="800dd-134">Todas las clases heredan del <xref:System.ServiceModel.Channels.SecurityBindingElement>, que incluye cuatro propiedades pertinentes:</span><span class="sxs-lookup"><span data-stu-id="800dd-134">All classes inherit from the <xref:System.ServiceModel.Channels.SecurityBindingElement>, which includes four relevant properties:</span></span>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### <a name="scopes"></a><span data-ttu-id="800dd-135">Ámbitos</span><span class="sxs-lookup"><span data-stu-id="800dd-135">Scopes</span></span>  

 <span data-ttu-id="800dd-136">Existen dos ámbitos para admitir las credenciales:</span><span class="sxs-lookup"><span data-stu-id="800dd-136">Two scopes exist for supporting credentials:</span></span>  
  
- <span data-ttu-id="800dd-137">Los *tokens auxiliares de extremo* admiten todas las operaciones de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="800dd-137">*Endpoint supporting tokens* support all operations of an endpoint.</span></span> <span data-ttu-id="800dd-138">Es decir, se puede utilizar la credencial que el token de aprobación representa siempre que se invoca una operación de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="800dd-138">That is, the credential that the supporting token represents can be used whenever any endpoint operations are invoked.</span></span>  
  
- <span data-ttu-id="800dd-139">Los *tokens auxiliares de operación* solo admiten una operación de punto de conexión específica.</span><span class="sxs-lookup"><span data-stu-id="800dd-139">*Operation supporting tokens* support only a specific endpoint operation.</span></span>  
  
 <span data-ttu-id="800dd-140">Tal y como han indicado los nombres de la propiedad, se puede requerir las credenciales de aprobación o estas pueden ser opcionales.</span><span class="sxs-lookup"><span data-stu-id="800dd-140">As indicated by the property names, supporting credentials can be either required or optional.</span></span> <span data-ttu-id="800dd-141">Es decir, si la credencial de aprobación se utiliza si está presente, aunque no es necesario, pero no se producirá un error en la autenticación si no está presente.</span><span class="sxs-lookup"><span data-stu-id="800dd-141">That is, if the supporting credential is used if it is present, although it is not necessary, but the authentication will not fail if it is not present.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="800dd-142">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="800dd-142">Procedures</span></span>  
  
#### <a name="to-create-a-custom-binding-that-includes-supporting-credentials"></a><span data-ttu-id="800dd-143">Para crear un enlace personalizado que incluye credenciales de aprobación</span><span class="sxs-lookup"><span data-stu-id="800dd-143">To create a custom binding that includes supporting credentials</span></span>  
  
1. <span data-ttu-id="800dd-144">Crear un elemento de enlace de seguridad.</span><span class="sxs-lookup"><span data-stu-id="800dd-144">Create a security binding element.</span></span> <span data-ttu-id="800dd-145">El ejemplo siguiente crea <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> con el modo de autenticación `UserNameForCertificate`.</span><span class="sxs-lookup"><span data-stu-id="800dd-145">The example below creates a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> with the `UserNameForCertificate` authentication mode.</span></span> <span data-ttu-id="800dd-146">Utilice el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="800dd-146">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A> method.</span></span>  
  
2. <span data-ttu-id="800dd-147">Agregue el parámetro de aprobación a la colección de tipos devuelta por la propiedad adecuada (`Endorsing`, `Signed`, `SignedEncrypted`o `SignedEndorsed`).</span><span class="sxs-lookup"><span data-stu-id="800dd-147">Add the supporting parameter to the collection of types returned by the appropriate property (`Endorsing`, `Signed`, `SignedEncrypted`, or `SignedEndorsed`).</span></span> <span data-ttu-id="800dd-148">Los tipos en el espacio de nombres <xref:System.ServiceModel.Security.Tokens> incluyen tipos utilizados normalmente, como <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="800dd-148">The types in the <xref:System.ServiceModel.Security.Tokens> namespace include commonly used types, such as the <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="800dd-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="800dd-149">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="800dd-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="800dd-150">Description</span></span>  

 <span data-ttu-id="800dd-151">En el ejemplo siguiente se crea una instancia de<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y agrega una instancia de la clase <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> a la colección que ha devuelto la propiedad endosada.</span><span class="sxs-lookup"><span data-stu-id="800dd-151">The following example creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and adds an instance of the <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> class to the collection the Endorsing property returned.</span></span>  
  
### <a name="code"></a><span data-ttu-id="800dd-152">Código</span><span class="sxs-lookup"><span data-stu-id="800dd-152">Code</span></span>  

 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="800dd-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="800dd-153">See also</span></span>

- [<span data-ttu-id="800dd-154">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="800dd-154">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
