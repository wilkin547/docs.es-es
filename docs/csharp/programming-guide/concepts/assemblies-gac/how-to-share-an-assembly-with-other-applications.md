---
title: 'Cómo: Compartir un ensamblado con otras aplicaciones (C#)'
ms.date: 07/20/2015
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: a5b20061c759fd914193f24aa123317f13d31dce
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266474"
---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a>Cómo: Compartir un ensamblado con otras aplicaciones (C#)
Los ensamblados pueden ser privados o compartidos: de forma predeterminada, la mayoría de los programas sencillos constan de un ensamblado privado porque no se diseñaron para ser usados por otras aplicaciones.  
  
 Para compartir un ensamblado con otras aplicaciones, debe colocarse en la [caché global de ensamblados](../../../../framework/app-domains/gac.md) (GAC).  
  
### <a name="sharing-an-assembly"></a>Compartir un ensamblado  
  
1.  Cree el ensamblado. Para obtener más información, vea [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md) (Crear ensamblados).  
  
2.  Asigne un nombre seguro al ensamblado. Para obtener más información, vea [Cómo: Firmar un ensamblado con un nombre seguro](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
3.  Asigne la información de versión al ensamblado. Para obtener más información, vea [Versiones de los ensamblados](../../../../../docs/framework/app-domains/assembly-versioning.md).  
  
4.  Agregue el ensamblado a la caché global de ensamblados. Para obtener más información, vea [Cómo: Instalar un ensamblado en la memoria caché global de ensamblados](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).  
  
5.  Obtenga acceso a los tipos contenidos en el ensamblado desde las otras aplicaciones. Para obtener más información, vea [Cómo: Hacer referencia a un ensamblado con nombre seguro](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../../csharp/programming-guide/index.md)  
- [Programar con ensamblados](../../../../framework/app-domains/programming-with-assemblies.md)
