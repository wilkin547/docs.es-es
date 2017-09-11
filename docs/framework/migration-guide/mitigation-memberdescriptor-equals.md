---
title: "Mitigación: MemberDescriptor.Equals"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf3735f0-0dd4-4bef-b4b0-575264e10f39
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4989d3c2611b500063158955f102931902e1ab32
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-memberdescriptorequals"></a><span data-ttu-id="3a029-102">Mitigación: MemberDescriptor.Equals</span><span class="sxs-lookup"><span data-stu-id="3a029-102">Mitigation: MemberDescriptor.Equals</span></span>
<span data-ttu-id="3a029-103">A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la implementación del método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="3a029-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the implementation of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method has changed.</span></span> <span data-ttu-id="3a029-104">Puesto que los métodos `System.ComponentModel.EventDescriptor.Equals` y  `System.ComponentModel.PropertyDescriptor.Equals` heredan la implementación de clase base, el cambio también afecta a estos métodos.</span><span class="sxs-lookup"><span data-stu-id="3a029-104">Because the `System.ComponentModel.EventDescriptor.Equals` and  `System.ComponentModel.PropertyDescriptor.Equals` methods inherit the base class implementation, the change also affects these methods.</span></span>  
  
 <span data-ttu-id="3a029-105">En aplicaciones que tienen como destino las versiones de .NET Framework anteriores a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], una parte de la prueba del método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> de igualdad se comparaba incorrectamente con la propiedad <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> de un objeto con la propiedad <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> de otro.</span><span class="sxs-lookup"><span data-stu-id="3a029-105">In apps that target versions of the .NET Framework prior to [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a portion of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method's test for equality  incorrectly compared the <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> property of one object with the <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> property of the other.</span></span> <span data-ttu-id="3a029-106">A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], el método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> compara la propiedad <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> de los dos objetos.</span><span class="sxs-lookup"><span data-stu-id="3a029-106">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method compares the <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> property of the two objects.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="3a029-107">Impacto</span><span class="sxs-lookup"><span data-stu-id="3a029-107">Impact</span></span>  
 <span data-ttu-id="3a029-108">Este cambio implementa correctamente la prueba de igualdad para los objetos <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName> y debe tener una repercusión mínima.</span><span class="sxs-lookup"><span data-stu-id="3a029-108">This change correctly implements the test for equality for <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName> objects and should have minimal impact.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="3a029-109">Mitigación</span><span class="sxs-lookup"><span data-stu-id="3a029-109">Mitigation</span></span>  
 <span data-ttu-id="3a029-110">Hay disponibles dos soluciones si la aplicación tiene como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o una versión posterior de .NET Framework, y depende del método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> que a veces devuelve `false` cuando los descriptores del miembro son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="3a029-110">Two workarounds are available if your app targets the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or a later version of the .NET Framework and it depends on the  <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method sometimes returning `false` when member descriptors are equivalent:</span></span>  
  
-   <span data-ttu-id="3a029-111">Puede rechazar este cambio sin modificar el código fuente agregando lo siguiente a la sección [ \<runtime >](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="3a029-111">You can opt out of this change without modifying your source code by adding the following to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value = "Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />  
     </runtime>  
    ```  
  
-   <span data-ttu-id="3a029-112">Puede modificar el código fuente para restablecer el comportamiento anterior. Para ello, compare manualmente las propiedades <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> y <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> después de llamar al método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>, como hace el siguiente fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="3a029-112">You can modify your source code to restore the previous behavior by manually comparing the  <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> and <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> properties after calling the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method, as the following code fragment does.</span></span>  
  
    ```csharp  
    if (memberDescriptor1.Equals(memberDescriptor2) &   
        memberDescriptor1.Description.Equals(memberDescriptor2.Category)) {  
          // Code to execute if true.  
    }  
    else {  
          // Code to execute if false.     
    }  
    ```  
  
    ```  
    If memberDescriptor1.Equals(memberDescriptor2) And   
        memberDescriptor1.Description.Equals(memberDescriptor2.Category)  
          // Code to execute if True.  
    Else  
          // Code to execute if False.     
    End If  
    ```  
  
 <span data-ttu-id="3a029-113">Para aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones anteriores, puede habilitar este cambio agregando el siguiente valor al archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="3a029-113">For apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, you can enable this change by adding the following value to your app.config file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a029-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a029-114">See Also</span></span>  
 <span data-ttu-id="3a029-115">[Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md) </span><span class="sxs-lookup"><span data-stu-id="3a029-115">[Retargeting Changes](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md) </span></span>  
 [<span data-ttu-id="3a029-116">Compatibilidad de aplicaciones en 4.6.2</span><span class="sxs-lookup"><span data-stu-id="3a029-116">Application Compatibility in 4.6.2</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)

