---
title: Procedimiento para crear una credencial de apoyo
ms.date: 03/30/2017
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
ms.openlocfilehash: b181ac72c9f197e9e404f7aa0f04e254abac10da
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557403"
---
# <a name="how-to-create-a-supporting-credential"></a><span data-ttu-id="6c71f-102">Procedimiento para crear una credencial de apoyo</span><span class="sxs-lookup"><span data-stu-id="6c71f-102">How to: Create a Supporting Credential</span></span>
<span data-ttu-id="6c71f-103">Es posible tener un esquema de seguridad personalizado que requiera más de una credencial.</span><span class="sxs-lookup"><span data-stu-id="6c71f-103">It is possible to have a custom security scheme that requires more than one credential.</span></span> <span data-ttu-id="6c71f-104">Por ejemplo, un servicio puede solicitar del cliente un nombre de usuario y contraseña, pero también una credencial que demuestre que el cliente tiene más de 18 años.</span><span class="sxs-lookup"><span data-stu-id="6c71f-104">For example, a service may demand from the client not just a user name and password, but also a credential that proves the client is over the age of 18.</span></span> <span data-ttu-id="6c71f-105">La segunda credencial es una *credencial de apoyo*.</span><span class="sxs-lookup"><span data-stu-id="6c71f-105">The second credential is a *supporting credential*.</span></span> <span data-ttu-id="6c71f-106">En este tema se explica cómo implementar estas credenciales en un cliente de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6c71f-106">This topic explains how to implement such credentials in an Windows Communication Foundation (WCF) client.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c71f-107">La especificación para admitir las credenciales forma parte de la especificación WS-SecurityPolicy.</span><span class="sxs-lookup"><span data-stu-id="6c71f-107">The specification for supporting credentials is part of the WS-SecurityPolicy specification.</span></span> <span data-ttu-id="6c71f-108">Para obtener más información, vea [Especificaciones de seguridad de servicios web](/previous-versions/dotnet/articles/ms951273(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="6c71f-108">For more information, see [Web Services Security Specifications](/previous-versions/dotnet/articles/ms951273(v=msdn.10)).</span></span>  
  
## <a name="supporting-tokens"></a><span data-ttu-id="6c71f-109">Tokens auxiliares</span><span class="sxs-lookup"><span data-stu-id="6c71f-109">Supporting Tokens</span></span>  
 <span data-ttu-id="6c71f-110">En Resumen, cuando se usa la seguridad de mensajes, siempre se usa una *credencial principal* para proteger el mensaje (por ejemplo, un certificado X. 509 o un vale de Kerberos).</span><span class="sxs-lookup"><span data-stu-id="6c71f-110">In brief, when you use message security, a *primary credential* is always used to secure the message (for example, an X.509 certificate or a Kerberos ticket).</span></span>  
  
 <span data-ttu-id="6c71f-111">Tal y como se define en la especificación, un enlace de seguridad utiliza *tokens* para proteger el intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="6c71f-111">As defined by the specification, a security binding uses *tokens* to secure the message exchange.</span></span> <span data-ttu-id="6c71f-112">Un *token* es una representación de una credencial de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6c71f-112">A *token* is a representation of a security credential.</span></span>  
  
 <span data-ttu-id="6c71f-113">El enlace de seguridad utiliza un token primario identificado en la directiva de enlace de seguridad para crear una firma.</span><span class="sxs-lookup"><span data-stu-id="6c71f-113">The security binding uses a primary token identified in the security binding policy to create a signature.</span></span> <span data-ttu-id="6c71f-114">Esta firma se conoce como la *firma del mensaje*.</span><span class="sxs-lookup"><span data-stu-id="6c71f-114">This signature is referred to as the *message signature*.</span></span>  
  
 <span data-ttu-id="6c71f-115">Los tokens adicionales se pueden especificar para aumentar las notificaciones proporcionadas por el token asociado a la firma del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6c71f-115">Additional tokens can be specified to augment the claims provided by the token associated with the message signature.</span></span>  
  
## <a name="endorsing-signing-and-encrypting"></a><span data-ttu-id="6c71f-116">Endosar, firmar y cifrar</span><span class="sxs-lookup"><span data-stu-id="6c71f-116">Endorsing, Signing, and Encrypting</span></span>  
 <span data-ttu-id="6c71f-117">Una credencial de apoyo da como resultado un *token auxiliar* que se transmite dentro del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6c71f-117">A supporting credential results in a *supporting token* transmitted inside the message.</span></span> <span data-ttu-id="6c71f-118">La especificación de WS-SecurityPolicy define cuatro maneras de adjuntar un token de aprobación al mensaje, tal y como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6c71f-118">The WS-SecurityPolicy specification defines four ways to attach a supporting token to the message, as described in the following table.</span></span>  
  
|<span data-ttu-id="6c71f-119">Propósito</span><span class="sxs-lookup"><span data-stu-id="6c71f-119">Purpose</span></span>|<span data-ttu-id="6c71f-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c71f-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c71f-121">Firmado</span><span class="sxs-lookup"><span data-stu-id="6c71f-121">Signed</span></span>|<span data-ttu-id="6c71f-122">El token de aprobación está incluido en el encabezado de seguridad y es firmado por la firma del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6c71f-122">The supporting token is included in the security header and is signed by the message signature.</span></span>|  
|<span data-ttu-id="6c71f-123">Endosar</span><span class="sxs-lookup"><span data-stu-id="6c71f-123">Endorsing</span></span>|<span data-ttu-id="6c71f-124">Un *token* de aprobación firma la firma del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6c71f-124">An *endorsing token* signs the message signature.</span></span>|  
|<span data-ttu-id="6c71f-125">Firmar y endosar</span><span class="sxs-lookup"><span data-stu-id="6c71f-125">Signed and Endorsing</span></span>|<span data-ttu-id="6c71f-126">Los tokens firmados y endosados firman el elemento `ds:Signature` completo generado a partir de la firma del mensaje y están firmados por esa firma del mensaje; es decir, ambos tokens (el token utilizado para la firma del mensaje y el token endosado y firmado) se firman entre sí.</span><span class="sxs-lookup"><span data-stu-id="6c71f-126">Signed, endorsing tokens sign the entire `ds:Signature` element produced from the message signature and are themselves signed by that message signature; that is, both tokens (the token used for the message signature and the signed endorsing token) sign each other.</span></span>|  
|<span data-ttu-id="6c71f-127">Firmar y cifrar</span><span class="sxs-lookup"><span data-stu-id="6c71f-127">Signed and Encrypting</span></span>|<span data-ttu-id="6c71f-128">Los tokens de aprobación firmados y cifrados son tokens de aprobación firmados que también se cifran cuando aparecen en `wsse:SecurityHeader`.</span><span class="sxs-lookup"><span data-stu-id="6c71f-128">Signed, encrypted supporting tokens are signed supporting tokens that are also encrypted when they appear in the `wsse:SecurityHeader`.</span></span>|  
  
## <a name="programming-supporting-credentials"></a><span data-ttu-id="6c71f-129">Programar credenciales de aprobación</span><span class="sxs-lookup"><span data-stu-id="6c71f-129">Programming Supporting Credentials</span></span>  
 <span data-ttu-id="6c71f-130">Para crear un servicio que use tokens auxiliares, debe crear un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6c71f-130">To create a service that uses supporting tokens you must create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span></span> <span data-ttu-id="6c71f-131">(Para obtener más información, consulte [Cómo: crear un enlace personalizado mediante SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)).</span><span class="sxs-lookup"><span data-stu-id="6c71f-131">(For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).)</span></span>  
  
 <span data-ttu-id="6c71f-132">El primer paso cuando se crea un enlace personalizado es crear un elemento de enlace de seguridad, que puede ser uno de tres tipos:</span><span class="sxs-lookup"><span data-stu-id="6c71f-132">The first step when creating a custom binding is to create a security binding element, which can be one of three types:</span></span>  
  
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="6c71f-133">Todas las clases heredan del <xref:System.ServiceModel.Channels.SecurityBindingElement>, que incluye cuatro propiedades pertinentes:</span><span class="sxs-lookup"><span data-stu-id="6c71f-133">All classes inherit from the <xref:System.ServiceModel.Channels.SecurityBindingElement>, which includes four relevant properties:</span></span>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### <a name="scopes"></a><span data-ttu-id="6c71f-134">Ámbitos</span><span class="sxs-lookup"><span data-stu-id="6c71f-134">Scopes</span></span>  
 <span data-ttu-id="6c71f-135">Existen dos ámbitos para admitir las credenciales:</span><span class="sxs-lookup"><span data-stu-id="6c71f-135">Two scopes exist for supporting credentials:</span></span>  
  
- <span data-ttu-id="6c71f-136">Los *tokens auxiliares de extremo* admiten todas las operaciones de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6c71f-136">*Endpoint supporting tokens* support all operations of an endpoint.</span></span> <span data-ttu-id="6c71f-137">Es decir, se puede utilizar la credencial que el token de aprobación representa siempre que se invoca una operación de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6c71f-137">That is, the credential that the supporting token represents can be used whenever any endpoint operations are invoked.</span></span>  
  
- <span data-ttu-id="6c71f-138">Los *tokens auxiliares de operación* solo admiten una operación de punto de conexión específica.</span><span class="sxs-lookup"><span data-stu-id="6c71f-138">*Operation supporting tokens* support only a specific endpoint operation.</span></span>  
  
 <span data-ttu-id="6c71f-139">Tal y como han indicado los nombres de la propiedad, se puede requerir las credenciales de aprobación o estas pueden ser opcionales.</span><span class="sxs-lookup"><span data-stu-id="6c71f-139">As indicated by the property names, supporting credentials can be either required or optional.</span></span> <span data-ttu-id="6c71f-140">Es decir, si la credencial de aprobación se utiliza si está presente, aunque no es necesario, pero no se producirá un error en la autenticación si no está presente.</span><span class="sxs-lookup"><span data-stu-id="6c71f-140">That is, if the supporting credential is used if it is present, although it is not necessary, but the authentication will not fail if it is not present.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="6c71f-141">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6c71f-141">Procedures</span></span>  
  
#### <a name="to-create-a-custom-binding-that-includes-supporting-credentials"></a><span data-ttu-id="6c71f-142">Para crear un enlace personalizado que incluye credenciales de aprobación</span><span class="sxs-lookup"><span data-stu-id="6c71f-142">To create a custom binding that includes supporting credentials</span></span>  
  
1. <span data-ttu-id="6c71f-143">Crear un elemento de enlace de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6c71f-143">Create a security binding element.</span></span> <span data-ttu-id="6c71f-144">El ejemplo siguiente crea <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> con el modo de autenticación `UserNameForCertificate`.</span><span class="sxs-lookup"><span data-stu-id="6c71f-144">The example below creates a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> with the `UserNameForCertificate` authentication mode.</span></span> <span data-ttu-id="6c71f-145">Utilice el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="6c71f-145">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A> method.</span></span>  
  
2. <span data-ttu-id="6c71f-146">Agregue el parámetro de aprobación a la colección de tipos devuelta por la propiedad adecuada (`Endorsing`, `Signed`, `SignedEncrypted`o `SignedEndorsed`).</span><span class="sxs-lookup"><span data-stu-id="6c71f-146">Add the supporting parameter to the collection of types returned by the appropriate property (`Endorsing`, `Signed`, `SignedEncrypted`, or `SignedEndorsed`).</span></span> <span data-ttu-id="6c71f-147">Los tipos en el espacio de nombres <xref:System.ServiceModel.Security.Tokens> incluyen tipos utilizados normalmente, como <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="6c71f-147">The types in the <xref:System.ServiceModel.Security.Tokens> namespace include commonly used types, such as the <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c71f-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c71f-148">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6c71f-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c71f-149">Description</span></span>  
 <span data-ttu-id="6c71f-150">En el ejemplo siguiente se crea una instancia de<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y agrega una instancia de la clase <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> a la colección que ha devuelto la propiedad endosada.</span><span class="sxs-lookup"><span data-stu-id="6c71f-150">The following example creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and adds an instance of the <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> class to the collection the Endorsing property returned.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6c71f-151">Código</span><span class="sxs-lookup"><span data-stu-id="6c71f-151">Code</span></span>  
 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6c71f-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c71f-152">See also</span></span>

- [<span data-ttu-id="6c71f-153">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="6c71f-153">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
