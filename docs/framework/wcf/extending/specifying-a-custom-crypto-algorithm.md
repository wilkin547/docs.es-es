---
title: Especificar un algoritmo criptográfico personalizado
ms.date: 03/30/2017
ms.assetid: d662a305-8e09-451d-9a59-b0f12b012f1d
ms.openlocfilehash: 673d177a665e265d77f0221e0a00f4b814c8795c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186488"
---
# <a name="specifying-a-custom-crypto-algorithm"></a><span data-ttu-id="ec7e3-102">Especificar un algoritmo criptográfico personalizado</span><span class="sxs-lookup"><span data-stu-id="ec7e3-102">Specifying a Custom Crypto Algorithm</span></span>
<span data-ttu-id="ec7e3-103">WCF permite especificar un algoritmo criptográfico personalizado para usarlo cuando se cifren datos o se calculen firmas digitales.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-103">WCF allows you to specify a custom crypto algorithm to use when encrypting data or computing digital signatures.</span></span> <span data-ttu-id="ec7e3-104">Para ello, se siguen estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ec7e3-104">This is done by the following steps:</span></span>  
  
1. <span data-ttu-id="ec7e3-105">Derivar una clase de la clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-105">Derive a class from <xref:System.ServiceModel.Security.SecurityAlgorithmSuite></span></span>  
  
2. <span data-ttu-id="ec7e3-106">Registrar el algoritmo</span><span class="sxs-lookup"><span data-stu-id="ec7e3-106">Register the algorithm</span></span>  
  
3. <span data-ttu-id="ec7e3-107">Configurar el enlace con la clase derivada de la clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-107">Configure the binding with the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-derived class.</span></span>  
  
## <a name="derive-a-class-from-securityalgorithmsuite"></a><span data-ttu-id="ec7e3-108">Derivar una clase de SecurityAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="ec7e3-108">Derive a class from SecurityAlgorithmSuite</span></span>  
 <span data-ttu-id="ec7e3-109">La clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> es una clase base abstracta derivada que permite especificar el algoritmo que se va a usar cuando se realicen distintas operaciones relacionadas con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-109">The <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> is an abstract base class that allows you to specify the algorithm to use when performing various security related operations.</span></span> <span data-ttu-id="ec7e3-110">Por ejemplo, calcular un hash para una firma digital o cifrar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-110">For example, computing a hash for a digital signature or encrypting a message.</span></span> <span data-ttu-id="ec7e3-111">En el código siguientes se muestra cómo derivar una clase de la clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>:</span><span class="sxs-lookup"><span data-stu-id="ec7e3-111">The following code shows how to derive a class from <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>:</span></span>  
  
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
  
## <a name="register-the-custom-algorithm"></a><span data-ttu-id="ec7e3-112">Registrar el algoritmo personalizado</span><span class="sxs-lookup"><span data-stu-id="ec7e3-112">Register the Custom Algorithm</span></span>  
 <span data-ttu-id="ec7e3-113">El registro se puede realizar en un archivo de configuración o en código imperativo.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-113">Registration can be done in a configuration file or in imperative code.</span></span> <span data-ttu-id="ec7e3-114">El registro de un algoritmo personalizado se lleva a cabo mediante la creación de una asignación entre una clase que implemente un proveedor de servicios criptográficos y un alias.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-114">Registering a custom algorithm is done by creating a mapping between a class that implements a crypto service provider and an alias.</span></span> <span data-ttu-id="ec7e3-115">A continuación, el alias se asigna a un URI que se usa cuando se especifica el algoritmo en el enlace del servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-115">The alias is then mapped to a URI which is used when specifying the algorithm in the WCF service’s binding.</span></span> <span data-ttu-id="ec7e3-116">En el siguiente fragmento de código de configuración se muestra cómo registrar un algoritmo personalizado en config:</span><span class="sxs-lookup"><span data-stu-id="ec7e3-116">The following configuration snippet illustrates how to register a custom algorithm in config:</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
           <cryptoClasses>  
              <cryptoClass SHA256CSP="System.Security.Cryptography.SHA256CryptoServiceProvider, System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
           </cryptoClasses>  
           <nameEntry name="http://constoso.com/CustomAlgorithms/CustomHashAlgorithm"  
              class="SHA256CSP" />  
           </cryptoNameMapping>  
        </cryptographySettings>  
    </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="ec7e3-117">La sección bajo `cryptoClasses` el <> elemento crea la asignación entre el SHA256CryptoServiceProvider y el alias "SHA256CSP".</span><span class="sxs-lookup"><span data-stu-id="ec7e3-117">The section under the <`cryptoClasses`> element creates the mapping between the SHA256CryptoServiceProvider and the alias "SHA256CSP".</span></span> <span data-ttu-id="ec7e3-118">El `nameEntry` elemento <> crea la asignación entre el alias "SHA256CSP" y la dirección URL `http://constoso.com/CustomAlgorithms/CustomHashAlgorithm`especificada.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-118">The <`nameEntry`> element creates the mapping between the "SHA256CSP" alias and the specified URL `http://constoso.com/CustomAlgorithms/CustomHashAlgorithm`.</span></span>  
  
 <span data-ttu-id="ec7e3-119">Use el método <xref:System.Security.Cryptography.CryptoConfig.AddAlgorithm(System.Type,System.String[])> para registrar el algoritmo personalizado en código.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-119">To register the custom algorithm in code use the <xref:System.Security.Cryptography.CryptoConfig.AddAlgorithm(System.Type,System.String[])> method.</span></span> <span data-ttu-id="ec7e3-120">Este método crea ambas asignaciones.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-120">This method creates both mappings.</span></span> <span data-ttu-id="ec7e3-121">En el ejemplo siguiente se muestra cómo llamar a este método:</span><span class="sxs-lookup"><span data-stu-id="ec7e3-121">The following example shows how to call this method:</span></span>  
  
```csharp
// Register the custom URI string defined for the hashAlgorithm in MyCustomAlgorithmSuite class to create the
// SHA256CryptoServiceProvider hash algorithm object.  
CryptoConfig.AddAlgorithm(typeof(SHA256CryptoServiceProvider), "http://constoso.com/CustomAlgorithms/CustomHashAlgorithm");  
```  
  
## <a name="configure-the-binding"></a><span data-ttu-id="ec7e3-122">Configurar el enlace</span><span class="sxs-lookup"><span data-stu-id="ec7e3-122">Configure the Binding</span></span>  
 <span data-ttu-id="ec7e3-123">Configure el enlace especificando la clase derivada de la clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> personalizada en la configuración del enlace como se muestra en el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="ec7e3-123">You configure the binding by specifying the custom <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-derived class in the binding settings as shown in the following code snippet:</span></span>  
  
```csharp  
WSHttpBinding binding = new WSHttpBinding();  
            binding.Security.Message.AlgorithmSuite = new MyCustomAlgorithmSuite();  
```  
  
 <span data-ttu-id="ec7e3-124">Para obtener un ejemplo de código completo, vea el [ejemplo de agilidad criptográfica en seguridad WCF.](../samples/cryptographic-agility-in-wcf-security.md)</span><span class="sxs-lookup"><span data-stu-id="ec7e3-124">For a complete code example, see the [Cryptographic Agility in WCF Security](../samples/cryptographic-agility-in-wcf-security.md) sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec7e3-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec7e3-125">See also</span></span>

- [<span data-ttu-id="ec7e3-126">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="ec7e3-126">Securing Services and Clients</span></span>](../feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ec7e3-127">Seguridad de servicios</span><span class="sxs-lookup"><span data-stu-id="ec7e3-127">Securing Services</span></span>](../securing-services.md)
- [<span data-ttu-id="ec7e3-128">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="ec7e3-128">Security Overview</span></span>](../feature-details/security-overview.md)
- [<span data-ttu-id="ec7e3-129">Conceptos de seguridad</span><span class="sxs-lookup"><span data-stu-id="ec7e3-129">Security Concepts</span></span>](../feature-details/security-concepts.md)
