---
description: Más información acerca de cómo especificar un algoritmo criptográfico personalizado
title: Especificar un algoritmo criptográfico personalizado
ms.date: 03/30/2017
ms.assetid: d662a305-8e09-451d-9a59-b0f12b012f1d
ms.openlocfilehash: 4d4cb525b46b33a0d0df8dd6a3db9e9fafe84f8f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643974"
---
# <a name="specifying-a-custom-crypto-algorithm"></a><span data-ttu-id="d3e31-103">Especificar un algoritmo criptográfico personalizado</span><span class="sxs-lookup"><span data-stu-id="d3e31-103">Specifying a Custom Crypto Algorithm</span></span>

<span data-ttu-id="d3e31-104">WCF permite especificar un algoritmo criptográfico personalizado para usarlo cuando se cifren datos o se calculen firmas digitales.</span><span class="sxs-lookup"><span data-stu-id="d3e31-104">WCF allows you to specify a custom crypto algorithm to use when encrypting data or computing digital signatures.</span></span> <span data-ttu-id="d3e31-105">Para ello, se siguen estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d3e31-105">This is done by the following steps:</span></span>  
  
1. <span data-ttu-id="d3e31-106">Derivar una clase de la clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="d3e31-106">Derive a class from <xref:System.ServiceModel.Security.SecurityAlgorithmSuite></span></span>  
  
2. <span data-ttu-id="d3e31-107">Registrar el algoritmo</span><span class="sxs-lookup"><span data-stu-id="d3e31-107">Register the algorithm</span></span>  
  
3. <span data-ttu-id="d3e31-108">Configurar el enlace con la clase derivada de la clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="d3e31-108">Configure the binding with the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-derived class.</span></span>  
  
## <a name="derive-a-class-from-securityalgorithmsuite"></a><span data-ttu-id="d3e31-109">Derivar una clase de SecurityAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="d3e31-109">Derive a class from SecurityAlgorithmSuite</span></span>  

 <span data-ttu-id="d3e31-110">La clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> es una clase base abstracta derivada que permite especificar el algoritmo que se va a usar cuando se realicen distintas operaciones relacionadas con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="d3e31-110">The <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> is an abstract base class that allows you to specify the algorithm to use when performing various security related operations.</span></span> <span data-ttu-id="d3e31-111">Por ejemplo, calcular un hash para una firma digital o cifrar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="d3e31-111">For example, computing a hash for a digital signature or encrypting a message.</span></span> <span data-ttu-id="d3e31-112">En el código siguientes se muestra cómo derivar una clase de la clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>:</span><span class="sxs-lookup"><span data-stu-id="d3e31-112">The following code shows how to derive a class from <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>:</span></span>  
  
```csharp  
public class MyCustomAlgorithmSuite : SecurityAlgorithmSuite  
    {  
        public override string DefaultAsymmetricKeyWrapAlgorithm  
        {  
            get { return SecurityAlgorithms.RsaOaepKeyWrap; }  
        }  
  
        public override string DefaultAsymmetricSignatureAlgorithm  
        {  
            get { return SecurityAlgorithms.RsaSha1Signature; }  
        }  
  
        public override string DefaultCanonicalizationAlgorithm  
        {  
            get { return SecurityAlgorithms.ExclusiveC14n; ; }  
        }  
  
        public override string DefaultDigestAlgorithm  
        {  
            get { return SecurityAlgorithms.MyCustomHashAlgorithm; }  
        }  
  
        public override string DefaultEncryptionAlgorithm  
        {  
            get { return SecurityAlgorithms.Aes128Encryption; }  
        }  
  
        public override int DefaultEncryptionKeyDerivationLength  
        {  
            get { return 128; }  
        }  
  
        public override int DefaultSignatureKeyDerivationLength  
        {  
            get { return 128; }  
        }  
  
        public override int DefaultSymmetricKeyLength  
        {  
            get { return 128; }  
        }  
  
        public override string DefaultSymmetricKeyWrapAlgorithm  
        {  
            get { return SecurityAlgorithms.Aes128Encryption; }  
        }  
  
        public override string DefaultSymmetricSignatureAlgorithm  
        {  
            get { return SecurityAlgorithms.HmacSha1Signature; }  
        }  
  
        public override bool IsAsymmetricKeyLengthSupported(int length)  
        {  
            return length >= 1024 && length <= 4096;  
        }  
  
        public override bool IsSymmetricKeyLengthSupported(int length)  
        {  
            return length >= 128 && length <= 256;  
        }  
    }  
```  
  
## <a name="register-the-custom-algorithm"></a><span data-ttu-id="d3e31-113">Registrar el algoritmo personalizado</span><span class="sxs-lookup"><span data-stu-id="d3e31-113">Register the Custom Algorithm</span></span>  

 <span data-ttu-id="d3e31-114">El registro se puede realizar en un archivo de configuración o en código imperativo.</span><span class="sxs-lookup"><span data-stu-id="d3e31-114">Registration can be done in a configuration file or in imperative code.</span></span> <span data-ttu-id="d3e31-115">El registro de un algoritmo personalizado se lleva a cabo mediante la creación de una asignación entre una clase que implemente un proveedor de servicios criptográficos y un alias.</span><span class="sxs-lookup"><span data-stu-id="d3e31-115">Registering a custom algorithm is done by creating a mapping between a class that implements a crypto service provider and an alias.</span></span> <span data-ttu-id="d3e31-116">A continuación, el alias se asigna a un URI que se usa cuando se especifica el algoritmo en el enlace del servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="d3e31-116">The alias is then mapped to a URI which is used when specifying the algorithm in the WCF service’s binding.</span></span> <span data-ttu-id="d3e31-117">En el siguiente fragmento de código de configuración se muestra cómo registrar un algoritmo personalizado en config:</span><span class="sxs-lookup"><span data-stu-id="d3e31-117">The following configuration snippet illustrates how to register a custom algorithm in config:</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
           <cryptoClasses>  
              <cryptoClass SHA256CSP="System.Security.Cryptography.SHA256CryptoServiceProvider, System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
           </cryptoClasses>  
           <nameEntry name="http://contoso.com/CustomAlgorithms/CustomHashAlgorithm"  
              class="SHA256CSP" />  
           </cryptoNameMapping>  
        </cryptographySettings>  
    </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="d3e31-118">La sección del elemento <`cryptoClasses`> crea la asignación entre SHA256CryptoServiceProvider y el alias "SHA256CSP".</span><span class="sxs-lookup"><span data-stu-id="d3e31-118">The section under the <`cryptoClasses`> element creates the mapping between the SHA256CryptoServiceProvider and the alias "SHA256CSP".</span></span> <span data-ttu-id="d3e31-119">El `nameEntry` elemento <> crea la asignación entre el alias "SHA256CSP" y la dirección URL especificada `http://contoso.com/CustomAlgorithms/CustomHashAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="d3e31-119">The <`nameEntry`> element creates the mapping between the "SHA256CSP" alias and the specified URL `http://contoso.com/CustomAlgorithms/CustomHashAlgorithm`.</span></span>  
  
 <span data-ttu-id="d3e31-120">Use el método <xref:System.Security.Cryptography.CryptoConfig.AddAlgorithm(System.Type,System.String[])> para registrar el algoritmo personalizado en código.</span><span class="sxs-lookup"><span data-stu-id="d3e31-120">To register the custom algorithm in code use the <xref:System.Security.Cryptography.CryptoConfig.AddAlgorithm(System.Type,System.String[])> method.</span></span> <span data-ttu-id="d3e31-121">Este método crea ambas asignaciones.</span><span class="sxs-lookup"><span data-stu-id="d3e31-121">This method creates both mappings.</span></span> <span data-ttu-id="d3e31-122">En el ejemplo siguiente se muestra cómo llamar a este método:</span><span class="sxs-lookup"><span data-stu-id="d3e31-122">The following example shows how to call this method:</span></span>  
  
```csharp
// Register the custom URI string defined for the hashAlgorithm in MyCustomAlgorithmSuite class to create the
// SHA256CryptoServiceProvider hash algorithm object.  
CryptoConfig.AddAlgorithm(typeof(SHA256CryptoServiceProvider), "http://contoso.com/CustomAlgorithms/CustomHashAlgorithm");  
```  
  
## <a name="configure-the-binding"></a><span data-ttu-id="d3e31-123">Configurar el enlace</span><span class="sxs-lookup"><span data-stu-id="d3e31-123">Configure the Binding</span></span>  

 <span data-ttu-id="d3e31-124">Configure el enlace especificando la clase derivada de la clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> personalizada en la configuración del enlace como se muestra en el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="d3e31-124">You configure the binding by specifying the custom <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-derived class in the binding settings as shown in the following code snippet:</span></span>  
  
```csharp  
WSHttpBinding binding = new WSHttpBinding();  
            binding.Security.Message.AlgorithmSuite = new MyCustomAlgorithmSuite();  
```  
  
 <span data-ttu-id="d3e31-125">Para obtener un ejemplo de código completo, vea el ejemplo de [agilidad criptográfica en la seguridad de WCF](../samples/cryptographic-agility-in-wcf-security.md) .</span><span class="sxs-lookup"><span data-stu-id="d3e31-125">For a complete code example, see the [Cryptographic Agility in WCF Security](../samples/cryptographic-agility-in-wcf-security.md) sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3e31-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3e31-126">See also</span></span>

- [<span data-ttu-id="d3e31-127">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d3e31-127">Securing Services and Clients</span></span>](../feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d3e31-128">Seguridad de servicios</span><span class="sxs-lookup"><span data-stu-id="d3e31-128">Securing Services</span></span>](../securing-services.md)
- [<span data-ttu-id="d3e31-129">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="d3e31-129">Security Overview</span></span>](../feature-details/security-overview.md)
- [<span data-ttu-id="d3e31-130">Conceptos de seguridad</span><span class="sxs-lookup"><span data-stu-id="d3e31-130">Security Concepts</span></span>](../feature-details/security-concepts.md)
