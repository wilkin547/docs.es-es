---
title: "Mitigación: MemberDescriptor.Equals | Microsoft Docs"
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 409f06f4dfbe7be50dd2c487e49d3d4d8a477539
ms.contentlocale: es-es
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-memberdescriptorequals"></a>Mitigación: MemberDescriptor.Equals
A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], ha cambiado la implementación del método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>. Puesto que los métodos `System.ComponentModel.EventDescriptor.Equals` y  `System.ComponentModel.PropertyDescriptor.Equals` heredan la implementación de clase base, el cambio también afecta a estos métodos.  
  
 En las aplicaciones que tienen como destino las versiones de .NET Framework anteriores a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], una parte de la prueba del método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> de igualdad se comparaba incorrectamente con la propiedad <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> de un objeto con la propiedad <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> de otro. A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], el método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> compara la propiedad <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> de los dos objetos.  
  
## <a name="impact"></a>Impacto  
 Este cambio implementa correctamente la prueba de igualdad para los objetos <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName> y debe tener una repercusión mínima.  
  
## <a name="mitigation"></a>Mitigación  
 Hay disponibles dos soluciones si la aplicación tiene como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o una versión posterior de .NET Framework, y depende del método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> que a veces devuelve `false` cuando los descriptores del miembro son equivalentes:  
  
-   Puede rechazar este cambio sin modificar el código fuente agregando lo siguiente a la sección [ \<runtime >](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:  
  
    ```xml  
  
    <runtime>  
        <AppContextSwitchOverrides value = "Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />  
     </runtime>  
  
    ```  
  
-   Puede modificar el código fuente para restablecer el comportamiento anterior comparando manualmente las propiedades <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> y <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> después de llamar al método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>, como hace el siguiente fragmento de código.  
  
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
  
 Para aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones anteriores, puede habilitar este cambio agregando el siguiente valor al archivo app.config:  
  
```xml  
  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true />  
</runtime>  
  
```  
  
## <a name="see-also"></a>Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)   
 [Compatibilidad de aplicaciones en 4.6.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)

