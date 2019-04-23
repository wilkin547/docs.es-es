---
title: Procedimiento Compartir un ensamblado con otras aplicaciones (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
ms.openlocfilehash: 520fe69d30ca55251ae7a19dcd7a1ea0c11e7bd5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59302224"
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a>Procedimiento Compartir un ensamblado con otras aplicaciones (Visual Basic)
Los ensamblados pueden ser privados o compartidos: de forma predeterminada, la mayoría de los programas sencillos constan de un ensamblado privado porque no se diseñaron para ser usados por otras aplicaciones.  
  
 Para compartir un ensamblado con otras aplicaciones, debe colocarse en la [caché global de ensamblados](../../../../framework/app-domains/gac.md) (GAC).  
  
### <a name="sharing-an-assembly"></a>Compartir un ensamblado  
  
1. Cree el ensamblado. Para obtener más información, vea [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md) (Crear ensamblados).  
  
2. Asigne un nombre seguro al ensamblado. Para obtener más información, vea [Cómo: Firmar un ensamblado con un nombre seguro](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
3. Asigne la información de versión al ensamblado. Para obtener más información, vea [Versiones de los ensamblados](../../../../framework/app-domains/assembly-versioning.md).  
  
4. Agregue el ensamblado a la caché global de ensamblados. Para obtener más información, vea [Cómo: Instalar un ensamblado en la caché global de ensamblados](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).  
  
5. Obtenga acceso a los tipos contenidos en el ensamblado desde las otras aplicaciones. Para obtener más información, vea [Cómo: Hacer referencia a un ensamblado con nombre seguro](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).  
  
## <a name="see-also"></a>Vea también

- [Conceptos de programación](../../../../visual-basic/programming-guide/concepts/index.md)
- [Ensamblados de .NET](../../../../standard/assembly/index.md)
- [Programar con ensamblados](../../../../framework/app-domains/programming-with-assemblies.md)
