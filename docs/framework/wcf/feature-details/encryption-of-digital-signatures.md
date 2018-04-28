---
title: Cifrado de firmas digitales
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- encryption of digital signatures [WCF]
- digital signatures [WCF], encryption
- digital signatures [WCF]
ms.assetid: 0868866d-40b4-4341-8e42-eee3b7f15b69
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aa6abc39159b14eae41e43de5a8976857b1d4c13
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="encryption-of-digital-signatures"></a><span data-ttu-id="e3e3a-102">Cifrado de firmas digitales</span><span class="sxs-lookup"><span data-stu-id="e3e3a-102">Encryption of Digital Signatures</span></span>
<span data-ttu-id="e3e3a-103">De forma predeterminada, un mensaje se cifra y se firma y la firma se cifra digitalmente.</span><span class="sxs-lookup"><span data-stu-id="e3e3a-103">By default, a message is signed and encrypted, and the signature is digitally encrypted.</span></span> <span data-ttu-id="e3e3a-104">Puede controlar esto creando un enlace personalizado con una instancia de <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y estableciendo la propiedad `MessageProtectionOrder` de cualquier clase en un valor de enumeración <xref:System.ServiceModel.Security.MessageProtectionOrder>.</span><span class="sxs-lookup"><span data-stu-id="e3e3a-104">You can control this by creating a custom binding with an instance of the <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> or the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and then setting the `MessageProtectionOrder` property of either class to a <xref:System.ServiceModel.Security.MessageProtectionOrder> enumeration value.</span></span> <span data-ttu-id="e3e3a-105">De manera predeterminada, es <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>.</span><span class="sxs-lookup"><span data-stu-id="e3e3a-105">The default is <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>.</span></span> <span data-ttu-id="e3e3a-106">Este proceso tarda entre un 10 y un 40 por ciento más que la simple firma y cifrado.</span><span class="sxs-lookup"><span data-stu-id="e3e3a-106">This process takes 10 to 40 percent longer than simply signing and encrypting.</span></span> <span data-ttu-id="e3e3a-107">Deshabilitar el cifrado de la firma, sin embargo, puede permitir a un atacante adivinar el contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e3e3a-107">Disabling encryption of the signature, however, might allow an attacker to guess the contents of the message.</span></span> <span data-ttu-id="e3e3a-108">Esto es posible porque el elemento de firma contiene el código hash del texto sin formato de cada parte del mensaje firmada.</span><span class="sxs-lookup"><span data-stu-id="e3e3a-108">This is possible because the signature element contains the hash code of the plain text of every signed part in the message.</span></span> <span data-ttu-id="e3e3a-109">Por ejemplo, aunque se cifra el cuerpo del mensaje de forma predeterminada, la firma no cifrada contiene el código hash del cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e3e3a-109">For example, although the message body is encrypted by default, the unencrypted signature contains the hash code of the message body.</span></span> <span data-ttu-id="e3e3a-110">Si el mensaje es pequeño, un atacante podría ser capaz de deducir el contenido.</span><span class="sxs-lookup"><span data-stu-id="e3e3a-110">If the message is small, an attacker might be able to deduce the contents.</span></span> <span data-ttu-id="e3e3a-111">Cifrar la firma reduce o elimina esta posibilidad.</span><span class="sxs-lookup"><span data-stu-id="e3e3a-111">Encrypting the signature reduces or eliminates this possibility.</span></span>  
  
 <span data-ttu-id="e3e3a-112">Por consiguiente, solo deshabilite el cifrado de la firma cuando el valor del contenido sea bajo y el aumento de rendimiento significativo, por ejemplo, al enviar archivos binarios de gran tamaño que no tienen implicaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e3e3a-112">Therefore, disable encryption of the signature only when the value of the content is low, and the performance gain will be significant, for example, when sending large binary files that have no security implications.</span></span>  
  
### <a name="to-disable-digital-signing"></a><span data-ttu-id="e3e3a-113">Para deshabilitar la firma digital</span><span class="sxs-lookup"><span data-stu-id="e3e3a-113">To disable digital signing</span></span>  
  
1.  <span data-ttu-id="e3e3a-114">Creará un control <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="e3e3a-114">Create a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span> <span data-ttu-id="e3e3a-115">Para obtener más información, consulte [Cómo: crear un personalizado de enlace con SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="e3e3a-115">For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
2.  <span data-ttu-id="e3e3a-116">Agregue <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> a la colección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="e3e3a-116">Add either an <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> or a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> to the binding collection.</span></span>  
  
3.  <span data-ttu-id="e3e3a-117">Establezca la propiedad <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> o establezca la propiedad <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.</span><span class="sxs-lookup"><span data-stu-id="e3e3a-117">Set the <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> property to <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>, or set the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> property to <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e3e3a-118"> cómo crear enlaces personalizados, consulte [crear enlaces](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="e3e3a-118"> creating custom bindings, see [Creating User-Defined Bindings](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e3e3a-119"> cómo crear un enlace personalizado para un modo de autenticación específico, consulte [Cómo: crear un SecurityBindingElement para un modo de autenticación especificado](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e3e3a-119"> creating a custom binding for a specific authentication mode, see [How to: Create a SecurityBindingElement for a Specified Authentication Mode](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3e3a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3e3a-120">See Also</span></span>  
 <xref:System.ServiceModel.Security.MessageProtectionOrder>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
 [<span data-ttu-id="e3e3a-121">Creación de un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="e3e3a-121">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="e3e3a-122">Creación de enlaces definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="e3e3a-122">Creating User-Defined Bindings</span></span>](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)  
 [<span data-ttu-id="e3e3a-123">Creación de un SecurityBindingElement para un modo de autenticación especificado</span><span class="sxs-lookup"><span data-stu-id="e3e3a-123">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
