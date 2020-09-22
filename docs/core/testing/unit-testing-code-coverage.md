---
title: Empleo de cobertura de código para pruebas unitarias
description: Aprenda a usar las capacidades de cobertura de código para pruebas unitarias de .NET.
author: IEvangelist
ms.author: dapine
ms.date: 07/01/2020
ms.openlocfilehash: 4d2c8f3db26eaabcb973378a349ef57912e92bfa
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538152"
---
# <a name="use-code-coverage-for-unit-testing"></a>Empleo de cobertura de código para pruebas unitarias

Las pruebas unitarias ayudan a garantizar la funcionalidad y proporcionan una forma de comprobar los esfuerzos de refactorización. La cobertura de código es una medida de la cantidad de código que ejecutan las pruebas unitarias, ya sean líneas, ramas o métodos. Por ejemplo, si tiene una aplicación sencilla con solo dos ramas condicionales de código (_rama a_ y _rama b_), una prueba unitaria que compruebe la _rama a_ condicional notifica una cobertura de código del 50 %.

En este artículo se habla del uso de la cobertura de código para pruebas unitarias con Coverlet y de la generación de informes con ReportGenerator. Aunque este artículo se centra en C# y xUnit como marco de pruebas, MSTest y NUnit también funcionan. Coverlet es un [proyecto de código abierto en GitHub](https://github.com/coverlet-coverage/coverlet) que proporciona un marco de cobertura de código multiplataforma para C#. [Coverlet](https://dotnetfoundation.org/projects/coverlet) es parte de .NET Foundation. Coverlet recopila datos de series de pruebas de cobertura de Cobertura, que se usan para la generación de informes.

Además, en este artículo se detalla cómo usar la información de cobertura de código recopilada de una serie de pruebas de Coverlet para generar un informe. La generación de informes es posible gracias a otro [proyecto de código abierto en GitHub: ReportGenerator](https://github.com/danielpalme/ReportGenerator). ReportGenerator convierte los informes de cobertura generados por Cobertura, entre otros, en informes legibles para el usuario en distintos formatos.

Este artículo se basa en el [proyecto de código fuente de ejemplo](/samples/dotnet/samples/unit-testing-code-coverage-cs), disponible en el explorador de ejemplos.

## <a name="system-under-test"></a>Sistema sometido a prueba

El "sistema sometido a prueba" se refiere al código en el que se están escribiendo las pruebas unitarias, que podría ser un objeto, un servicio o cualquier otro elemento que exponga funcionalidad que se puede probar. En este artículo se va a crear una biblioteca de clases que va a ser el sistema sometido a prueba y dos proyectos de prueba unitaria correspondientes.

### <a name="create-a-class-library"></a>Creación de una biblioteca de clases

Desde un símbolo del sistema de un nuevo directorio denominado `UnitTestingCodeCoverage`, cree una nueva biblioteca de clases de .NET Standard con el comando [`dotnet new classlib`](../tools/dotnet-new.md#classlib):

```dotnetcli
dotnet new classlib -n Numbers
```

El siguiente fragmento de código define una clase `PrimeService` simple que proporciona funcionalidad para comprobar si un número es primo. Copie el fragmento de código siguiente y reemplace el contenido del archivo *Class1.cs* creado automáticamente en el directorio *Numbers*. Cambie el nombre del archivo *Class1.cs* a *PrimeService.cs*.

```csharp
namespace System.Numbers
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            if (candidate < 2)
            {
                return false;
            }

            for (int divisor = 2; divisor <= Math.Sqrt(candidate); ++divisor)
            {
                if (candidate % divisor == 0)
                {
                    return false;
                }
            }
            return true;
        }
    }
}
```

> [!TIP]
> Merece la pena mencionar que la biblioteca de clases `Numbers` se ha agregado a propósito al espacio de nombres `System`. Esto permite que <xref:System.Math?displayProperty=fullName> sea accesible sin una declaración de espacio de nombres `using System;`. Para obtener más información, vea [namespace (Referencia de C#)](../../csharp/language-reference/keywords/namespace.md).

### <a name="create-test-projects"></a>Creación de proyectos de prueba

Cree dos nuevas plantillas **Proyecto de pruebas xUnit (.NET Core)** desde el mismo símbolo del sistema con el comando [`dotnet new xunit`](../tools/dotnet-new.md#test):

```dotnetcli
dotnet new xunit -n XUnit.Coverlet.Collector
```

```dotnetcli
dotnet new xunit -n XUnit.Coverlet.MSBuild
```

Los dos proyectos de pruebas xUnit recién creados necesitan agregar una referencia de proyecto de la biblioteca de clases *Numbers*, de modo que los proyectos de pruebas tengan acceso a *PrimeService* para las pruebas. Desde el símbolo del sistema, use el comando [`dotnet add`](../tools/dotnet-add-reference.md):

```dotnetcli
dotnet add XUnit.Coverlet.Collector\XUnit.Coverlet.Collector.csproj reference Numbers\Numbers.csproj
```

```dotnetcli
dotnet add XUnit.Coverlet.MSBuild\XUnit.Coverlet.MSBuild.csproj reference Numbers\Numbers.csproj
```

El nombre del proyecto *MSBuild* es correcto, ya que depende del paquete NuGet [coverlet.msbuild](https://www.nuget.org/packages/coverlet.msbuild). Agregue esta dependencia de paquete mediante la ejecución del comando [`dotnet add package`](../tools/dotnet-add-package.md):

```dotnetcli
cd XUnit.Coverlet.MSBuild && dotnet add package coverlet.msbuild && cd ..
```

El comando anterior ha cambiado el ámbito de los directorios al proyecto de prueba *MSBuild* y ha agregado el paquete NuGet. Una vez hecho esto, se han cambiado los directorios, avanzando un nivel.

Abra los dos archivos *UnitTest1.cs* y reemplace su contenido por el siguiente fragmento de código. Cambie el nombre de los archivos *UnitTest1.cs* a *PrimeServiceTests.cs*.

```csharp
using System.Numbers;
using Xunit;

namespace XUnit.Coverlet
{
    public class PrimeServiceTests
    {
        readonly PrimeService _primeService;

        public PrimeServiceTests() => _primeService = new PrimeService();

        [
            Theory,
            InlineData(-1), InlineData(0), InlineData(1)
        ]
        public void IsPrime_ValuesLessThan2_ReturnFalse(int value) =>
            Assert.False(_primeService.IsPrime(value), $"{value} should not be prime");

        [
            Theory,
            InlineData(2), InlineData(3), InlineData(5), InlineData(7)
        ]
        public void IsPrime_PrimesLessThan10_ReturnTrue(int value) =>
            Assert.True(_primeService.IsPrime(value), $"{value} should be prime");

        [
            Theory,
            InlineData(4), InlineData(6), InlineData(8), InlineData(9)
        ]
        public void IsPrime_NonPrimesLessThan10_ReturnFalse(int value) =>
            Assert.False(_primeService.IsPrime(value), $"{value} should not be prime");
    }
}
```

### <a name="create-a-solution"></a>Crear una solución

Desde el símbolo del sistema, cree una nueva solución para encapsular la biblioteca de clases y los dos proyectos de prueba. Uso del comando [`dotnet sln`](../tools/dotnet-sln.md):

```dotnetcli
dotnet new sln -n XUnit.Coverage
```

Se crea un nuevo nombre de archivo de solución `XUnit.Coverage` en el directorio *UnitTestingCodeCoverage*. Agregue los proyectos a la raíz de la solución.

## <a name="linux"></a>[Linux](#tab/linux)

```dotnetcli
dotnet sln XUnit.Coverage.sln add **/*.csproj --in-root
```

## <a name="windows"></a>[Windows](#tab/windows)

```dotnetcli
dotnet sln XUnit.Coverage.sln add (ls **/*.csproj) --in-root
```

---

Compile la solución mediante el comando [`dotnet build`](../tools/dotnet-build.md):

```dotnetcli
dotnet build
```

Si la compilación se realiza correctamente, ha creado los tres proyectos, ha hecho referencia adecuadamente a los proyectos y paquetes y ha actualizado el código fuente de forma correcta. ¡Bien hecho!

## <a name="tooling"></a>Tooling

Hay dos tipos de herramientas de cobertura de código:

- **Recopiladores de datos:** los recopiladores de datos supervisan la ejecución de pruebas y recopilan información sobre las series de pruebas. Notifican la información recopilada en diversos formatos de salida, como XML y JSON. Para obtener más información, vea [Primer recopilador de datos](https://github.com/Microsoft/vstest-docs/blob/master/docs/extensions/datacollector.md).
- **Generadores de pruebas:** use los datos recopilados de las series de pruebas para generar informes, a menudo como HTML con estilo.

Esta sección se centra en las herramientas de recopilación de datos. A fin de usar Coverlet para la cobertura de código, un proyecto de prueba unitaria existente debe tener las dependencias de paquete adecuadas, o bien depender de [herramientas globales de .NET](../tools/global-tools.md) y el paquete NuGet [coverlet.console](https://www.nuget.org/packages/coverlet.console) correspondiente.

## <a name="integrate-with-net-test"></a>Integración con pruebas de .NET

La plantilla de proyecto de prueba xUnit ya está integrada con [coverlet.collector](https://www.nuget.org/packages/coverlet.collector) de forma predeterminada.
Desde el símbolo del sistema, cambie los directorios al proyecto *XUnit.Coverlet.Collector* y ejecute el comando [`dotnet test`](../tools/dotnet-test.md):

```dotnetcli
cd XUnit.Coverlet.Collector && dotnet test --collect:"XPlat Code Coverage"
```

> [!NOTE]
> El argumento `"XPlat Code Coverage"` es un nombre descriptivo que corresponde a los recopiladores de datos de Coverlet. Este nombre es necesario, aunque no distingue mayúsculas de minúsculas.

Como parte de la ejecución de `dotnet test`, se genera un archivo *coverage.cobertura.xml* resultante en el directorio *TestResults*. El archivo XML contiene los resultados. Se trata de una opción multiplataforma basada en la CLI de .NET Core que es ideal para los sistemas de compilación cuando MSBuild no está disponible.

A continuación se muestra el archivo de ejemplo *coverage.cobertura.xml*.

```xml
<?xml version="1.0" encoding="utf-8"?>
<coverage line-rate="1" branch-rate="1" version="1.9" timestamp="1592248008"
          lines-covered="12" lines-valid="12" branches-covered="6" branches-valid="6">
  <sources>
    <source>C:\</source>
  </sources>
  <packages>
    <package name="Numbers" line-rate="1" branch-rate="1" complexity="6">
      <classes>
        <class name="Numbers.PrimeService" line-rate="1" branch-rate="1" complexity="6"
               filename="Numbers\PrimeService.cs">
          <methods>
            <method name="IsPrime" signature="(System.Int32)" line-rate="1"
                    branch-rate="1" complexity="6">
              <lines>
                <line number="8" hits="11" branch="False" />
                <line number="9" hits="11" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="7" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="10" hits="3" branch="False" />
                <line number="11" hits="3" branch="False" />
                <line number="14" hits="22" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="57" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="15" hits="7" branch="False" />
                <line number="16" hits="7" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="27" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="17" hits="4" branch="False" />
                <line number="18" hits="4" branch="False" />
                <line number="20" hits="3" branch="False" />
                <line number="21" hits="4" branch="False" />
                <line number="23" hits="11" branch="False" />
              </lines>
            </method>
          </methods>
          <lines>
            <line number="8" hits="11" branch="False" />
            <line number="9" hits="11" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="7" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="10" hits="3" branch="False" />
            <line number="11" hits="3" branch="False" />
            <line number="14" hits="22" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="57" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="15" hits="7" branch="False" />
            <line number="16" hits="7" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="27" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="17" hits="4" branch="False" />
            <line number="18" hits="4" branch="False" />
            <line number="20" hits="3" branch="False" />
            <line number="21" hits="4" branch="False" />
            <line number="23" hits="11" branch="False" />
          </lines>
        </class>
      </classes>
    </package>
  </packages>
</coverage>
```

> [!TIP]
> Como alternativa, puede usar el paquete MSBuild si el sistema de compilación ya usa MSBuild. Desde el símbolo del sistema, cambie los directorios al proyecto *XUnit.Coverlet.MSBuild* y ejecute el comando `dotnet test`:
>
> ```dotnetcli
> dotnet test /p:CollectCoverage=true /p:CoverletOutputFormat=cobertura
> ```
>
> Se genera el archivo *coverage.cobertura.xml* resultante.  
> Puede seguir la guía de integración de msbuild [aquí](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/MSBuildIntegration.md).

## <a name="generate-reports"></a>Generación de informes

Ahora que puede recopilar datos de las series de pruebas unitarias, puede generar informes mediante [ReportGenerator](https://github.com/danielpalme/ReportGenerator). Para instalar el paquete NuGet [ReportGenerator](https://www.nuget.org/packages/dotnet-reportgenerator-globaltool) como una [herramienta global de .NET](../tools/global-tools.md), use el comando [`dotnet tool install`](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install -g dotnet-reportgenerator-globaltool
```

Ejecute la herramienta y proporcione las opciones deseadas según el archivo *coverage.cobertura.xml* de salida de la serie de pruebas anterior.

```console
reportgenerator
"-reports:Path\To\TestProject\TestResults\{guid}\coverage.cobertura.xml"
"-targetdir:coveragereport"
-reporttypes:Html
```

Después de ejecutar este comando, un archivo HTML representa el informe generado.

:::image type="content" source="media/test-report.png" lightbox="media/test-report.png" alt-text="Informe generado por las pruebas unitarias":::

## <a name="see-also"></a>Vea también

- [Cobertura de código de pruebas unitarias de Visual Studio](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested)
- [Repositorio de GitHub: Coverlet](https://github.com/coverlet-coverage/coverlet)
- [Repositorio de GitHub: ReportGenerator](https://github.com/danielpalme/ReportGenerator)
- [Sitio de proyecto de ReportGenerator](https://danielpalme.github.io/ReportGenerator)
- [Comando test de la CLI de .NET Core](../tools/dotnet-test.md)
- [Código fuente de ejemplo](/samples/dotnet/samples/unit-testing-code-coverage-cs)

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Procedimientos recomendados para las pruebas unitarias](unit-testing-best-practices.md)
