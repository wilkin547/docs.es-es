---
title: Procedimiento para cargar y descargar ensamblados
ms.date: 08/19/2019
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
ms.openlocfilehash: a520ffd41c3465737be7494d374cbcf64e3f1b85
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155781"
---
# <a name="how-to-load-and-unload-assemblies"></a>Procedimiento Carga y descarga de ensamblados
Common Language Runtime cargará automáticamente los ensamblados a los que hace referencia el programa, pero también es posible cargar dinámicamente ensamblados específicos en el dominio de aplicación actual. Para obtener más información, vea [Cómo: Cargar ensamblados en un dominio de aplicación](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).

No existe ninguna forma de descargar un ensamblado individual sin descargar todos los dominios de aplicación que lo contienen en .NET Framework. Aunque el ensamblado esté fuera de ámbito, el archivo de ensamblado actual permanecerá cargado hasta que se descarguen todos los dominios de aplicación que lo contienen. En .NET Core, la clase <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> controla la descarga de ensamblados. Para obtener más información, consulte [Uso y depuración de la descargabilidad de ensamblado en .NET Core](unloadability.md).

## <a name="load-and-unload-assemblies"></a>Carga y descarga de ensamblados

Para cargar un ensamblado en un dominio de aplicación, use uno de los diversos métodos de carga incluidos en las clases <xref:System.AppDomain> y <xref:System.Reflection.Assembly>. Para obtener más información, vea [Cómo: Cargar ensamblados en un dominio de aplicación](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md). Tenga en cuenta que .NET Core solo admite un único dominio de aplicación.

Para descargar un ensamblado en .NET Framework, debe descargar todos los dominios de aplicación que lo contienen. Para descargar un dominio de aplicación, use el método <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>. Para obtener más información, vea [Cómo: Descargar un dominio de aplicación](../../framework/app-domains/how-to-unload-an-application-domain.md).

Si quiere descargar algunos ensamblados en una aplicación de .NET Framework, pero no otros, considere la posibilidad de crear un nuevo dominio de aplicación, ejecutar el código en el dominio y, a continuación, descargar ese dominio de aplicación. Para obtener más información, vea [Cómo: Descargar un dominio de aplicación](../../framework/app-domains/how-to-unload-an-application-domain.md).  

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../csharp/programming-guide/index.md)
- [Conceptos de programación (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
- [Ensamblados de .NET](index.md)
- [Cómo: Cargar ensamblados en un dominio de aplicación](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
