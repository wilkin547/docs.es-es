---
title: Ejemplos de REF CURSOR
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c257da03-c6c9-4cf8-b591-b7740a962c40
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 112f544531bfeed3aa791fa9215e316f05f99169
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ref-cursor-examples"></a><span data-ttu-id="bb45b-102">Ejemplos de REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="bb45b-102">REF CURSOR Examples</span></span>
<span data-ttu-id="bb45b-103">Los ejemplos de cursores REF CURSOR constan de los siguientes tres ejemplos de Microsoft Visual Basic que muestran el uso de los cursores REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="bb45b-103">The REF CURSOR examples are comprised of the following three Microsoft Visual Basic examples that demonstrate using REF CURSORs.</span></span>  
  
|<span data-ttu-id="bb45b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bb45b-104">Sample</span></span>|<span data-ttu-id="bb45b-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb45b-105">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb45b-106">Parámetros REF CURSOR en un objeto OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="bb45b-106">REF CURSOR Parameters in an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)|<span data-ttu-id="bb45b-107">En este ejemplo se ejecuta un procedimiento almacenado PL/SQL que devuelve un parámetro REF CURSOR y lee el valor como un <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="bb45b-107">This example executes a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>|  
|[<span data-ttu-id="bb45b-108">Recuperación de datos de varios cursores REF cursor utilizando un objeto OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="bb45b-108">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)|<span data-ttu-id="bb45b-109">Este ejemplo ejecuta un procedimiento almacenado PL/SQL que devuelve dos parámetros REF CURSOR y lee los valores mediante un **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="bb45b-109">This example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>|  
|[<span data-ttu-id="bb45b-110">Rellenar un conjunto de datos con uno o varios parámetros REF cursor</span><span class="sxs-lookup"><span data-stu-id="bb45b-110">Filling a DataSet Using One or More REF CURSORs</span></span>](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)|<span data-ttu-id="bb45b-111">En este ejemplo se ejecuta un procedimiento almacenado PL/SQL que devuelve dos parámetros REF CURSOR y llena un <xref:System.Data.DataSet> con las filas que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="bb45b-111">This example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>|  
  
 <span data-ttu-id="bb45b-112">Para utilizar estos ejemplos, puede que tenga que crear las tablas de Oracle, y deberá crear un paquete PL/SQL y el cuerpo del paquete.</span><span class="sxs-lookup"><span data-stu-id="bb45b-112">To use these examples, you may need to create the Oracle tables, and you must create a PL/SQL package and package body.</span></span>  
  
## <a name="creating-the-oracle-tables"></a><span data-ttu-id="bb45b-113">Creación de las tablas de Oracle</span><span class="sxs-lookup"><span data-stu-id="bb45b-113">Creating the Oracle Tables</span></span>  
 <span data-ttu-id="bb45b-114">En estos ejemplos se utilizan tablas que se definen en el esquema Scott/Tiger de Oracle.</span><span class="sxs-lookup"><span data-stu-id="bb45b-114">These examples use tables that are defined in the Oracle Scott/Tiger schema.</span></span> <span data-ttu-id="bb45b-115">El esquema Scott/Tiger de Oracle se incluye en la mayoría de las instalaciones de Oracle.</span><span class="sxs-lookup"><span data-stu-id="bb45b-115">The Oracle Scott/Tiger schema is included with most Oracle installations.</span></span> <span data-ttu-id="bb45b-116">Si no existe este esquema, puede utilizar el archivo de comandos SQL situado en {OracleHome}\rdbms\admin\scott.sql para crear las tablas y los índices necesarios para estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="bb45b-116">If this schema does not exist, you can use the SQL commands file in {OracleHome}\rdbms\admin\scott.sql to create the tables and indexes used by these examples.</span></span>  
  
## <a name="creating-the-oracle-package-and-package-body"></a><span data-ttu-id="bb45b-117">Creación del paquete de Oracle y el cuerpo del paquete</span><span class="sxs-lookup"><span data-stu-id="bb45b-117">Creating the Oracle Package and Package Body</span></span>  
 <span data-ttu-id="bb45b-118">En estos ejemplos es necesario el siguiente paquete PL/SQL y cuerpo del paquete en el servidor.</span><span class="sxs-lookup"><span data-stu-id="bb45b-118">These examples require the following PL/SQL package and package body on your server.</span></span> <span data-ttu-id="bb45b-119">Cree el siguiente paquete de Oracle en el servidor de Oracle.</span><span class="sxs-lookup"><span data-stu-id="bb45b-119">Create the following Oracle package on the Oracle server.</span></span>  
  
```  
CREATE OR REPLACE PACKAGE CURSPKG AS   
    TYPE T_CURSOR IS REF CURSOR;   
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,   
                               IO_CURSOR IN OUT T_CURSOR);   
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
                                DEPTCURSOR OUT T_CURSOR);  
END CURSPKG;  
/   
```  
  
 <span data-ttu-id="bb45b-120">Cree el siguiente cuerpo del paquete de Oracle en el servidor Oracle.</span><span class="sxs-lookup"><span data-stu-id="bb45b-120">Create the following Oracle package body on the Oracle server.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="bb45b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb45b-121">See Also</span></span>  
 [<span data-ttu-id="bb45b-122">Cursores REF cursor de Oracle</span><span class="sxs-lookup"><span data-stu-id="bb45b-122">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 [<span data-ttu-id="bb45b-123">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="bb45b-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
