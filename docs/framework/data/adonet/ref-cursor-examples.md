---
description: 'Más información sobre: ejemplos de CURSOR REF'
title: Ejemplos de REF CURSOR
ms.date: 03/30/2017
ms.assetid: c257da03-c6c9-4cf8-b591-b7740a962c40
ms.openlocfilehash: e7cb411778b325400d37511b082032e590b339c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773230"
---
# <a name="ref-cursor-examples"></a><span data-ttu-id="99f29-103">Ejemplos de REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="99f29-103">REF CURSOR Examples</span></span>

<span data-ttu-id="99f29-104">Los ejemplos de cursores REF CURSOR constan de los siguientes tres ejemplos de Microsoft Visual Basic que muestran el uso de los cursores REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="99f29-104">The REF CURSOR examples are comprised of the following three Microsoft Visual Basic examples that demonstrate using REF CURSORs.</span></span>  
  
|<span data-ttu-id="99f29-105">Muestra</span><span class="sxs-lookup"><span data-stu-id="99f29-105">Sample</span></span>|<span data-ttu-id="99f29-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="99f29-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="99f29-107">Parámetros REF CURSOR en un objeto OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="99f29-107">REF CURSOR Parameters in an OracleDataReader</span></span>](ref-cursor-parameters-in-an-oracledatareader.md)|<span data-ttu-id="99f29-108">En este ejemplo se ejecuta un procedimiento almacenado PL/SQL que devuelve un parámetro REF CURSOR y lee el valor como un <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="99f29-108">This example executes a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>|  
|[<span data-ttu-id="99f29-109">Recuperar datos desde varios parámetros REF CURSOR utilizando un objeto OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="99f29-109">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](retrieving-data-from-multiple-ref-cursors.md)|<span data-ttu-id="99f29-110">En este ejemplo se ejecuta un procedimiento almacenado PL/SQL que devuelve dos parámetros REF CURSOR y Lee los valores mediante un **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="99f29-110">This example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>|  
|[<span data-ttu-id="99f29-111">Rellenar un conjunto de datos utilizando uno o varios parámetros REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="99f29-111">Filling a DataSet Using One or More REF CURSORs</span></span>](filling-a-dataset-using-one-or-more-ref-cursors.md)|<span data-ttu-id="99f29-112">En este ejemplo se ejecuta un procedimiento almacenado PL/SQL que devuelve dos parámetros REF CURSOR y llena un <xref:System.Data.DataSet> con las filas que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="99f29-112">This example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>|  
  
 <span data-ttu-id="99f29-113">Para utilizar estos ejemplos, puede que tenga que crear las tablas de Oracle, y deberá crear un paquete PL/SQL y el cuerpo del paquete.</span><span class="sxs-lookup"><span data-stu-id="99f29-113">To use these examples, you may need to create the Oracle tables, and you must create a PL/SQL package and package body.</span></span>  
  
## <a name="creating-the-oracle-tables"></a><span data-ttu-id="99f29-114">Creación de las tablas de Oracle</span><span class="sxs-lookup"><span data-stu-id="99f29-114">Creating the Oracle Tables</span></span>  

 <span data-ttu-id="99f29-115">En estos ejemplos se utilizan tablas que se definen en el esquema Scott/Tiger de Oracle.</span><span class="sxs-lookup"><span data-stu-id="99f29-115">These examples use tables that are defined in the Oracle Scott/Tiger schema.</span></span> <span data-ttu-id="99f29-116">El esquema Scott/Tiger de Oracle se incluye en la mayoría de las instalaciones de Oracle.</span><span class="sxs-lookup"><span data-stu-id="99f29-116">The Oracle Scott/Tiger schema is included with most Oracle installations.</span></span> <span data-ttu-id="99f29-117">Si no existe este esquema, puede utilizar el archivo de comandos SQL situado en {OracleHome}\rdbms\admin\scott.sql para crear las tablas y los índices necesarios para estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="99f29-117">If this schema does not exist, you can use the SQL commands file in {OracleHome}\rdbms\admin\scott.sql to create the tables and indexes used by these examples.</span></span>  
  
## <a name="creating-the-oracle-package-and-package-body"></a><span data-ttu-id="99f29-118">Creación del paquete de Oracle y el cuerpo del paquete</span><span class="sxs-lookup"><span data-stu-id="99f29-118">Creating the Oracle Package and Package Body</span></span>  

 <span data-ttu-id="99f29-119">En estos ejemplos es necesario el siguiente paquete PL/SQL y cuerpo del paquete en el servidor.</span><span class="sxs-lookup"><span data-stu-id="99f29-119">These examples require the following PL/SQL package and package body on your server.</span></span> <span data-ttu-id="99f29-120">Cree el siguiente paquete de Oracle en el servidor de Oracle.</span><span class="sxs-lookup"><span data-stu-id="99f29-120">Create the following Oracle package on the Oracle server.</span></span>  
  
```sql
CREATE OR REPLACE PACKAGE CURSPKG AS
    TYPE T_CURSOR IS REF CURSOR;
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,
                               IO_CURSOR IN OUT T_CURSOR);
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,
                                DEPTCURSOR OUT T_CURSOR);  
END CURSPKG;  
/
```  
  
 <span data-ttu-id="99f29-121">Cree el siguiente cuerpo del paquete de Oracle en el servidor Oracle.</span><span class="sxs-lookup"><span data-stu-id="99f29-121">Create the following Oracle package body on the Oracle server.</span></span>  
  
```sql
CREATE OR REPLACE PACKAGE BODY CURSPKG AS  
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,  
                               IO_CURSOR IN OUT T_CURSOR)  
    IS
        V_CURSOR T_CURSOR;
    BEGIN
        IF N_EMPNO <> 0
        THEN  
             OPEN V_CURSOR FOR
             SELECT EMP.EMPNO, EMP.ENAME, DEPT.DEPTNO, DEPT.DNAME
                  FROM EMP, DEPT
                  WHERE EMP.DEPTNO = DEPT.DEPTNO
                  AND EMP.EMPNO = N_EMPNO;  
  
        ELSE
             OPEN V_CURSOR FOR
             SELECT EMP.EMPNO, EMP.ENAME, DEPT.DEPTNO, DEPT.DNAME
                  FROM EMP, DEPT
                  WHERE EMP.DEPTNO = DEPT.DEPTNO;  
  
        END IF;  
        IO_CURSOR := V_CURSOR;
    END OPEN_ONE_CURSOR;
  
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,  
                                DEPTCURSOR OUT T_CURSOR)  
    IS
        V_CURSOR1 T_CURSOR;
        V_CURSOR2 T_CURSOR;
    BEGIN
        OPEN V_CURSOR1 FOR SELECT * FROM EMP;  
        OPEN V_CURSOR2 FOR SELECT * FROM DEPT;  
        EMPCURSOR  := V_CURSOR1;
        DEPTCURSOR := V_CURSOR2;
    END OPEN_TWO_CURSORS;
END CURSPKG;  
/  
```  
  
## <a name="see-also"></a><span data-ttu-id="99f29-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="99f29-122">See also</span></span>

- [<span data-ttu-id="99f29-123">Parámetros REF CURSOR de Oracle</span><span class="sxs-lookup"><span data-stu-id="99f29-123">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)
- [<span data-ttu-id="99f29-124">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="99f29-124">ADO.NET Overview</span></span>](ado-net-overview.md)
