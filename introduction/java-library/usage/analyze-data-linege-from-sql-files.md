# Analyze data linege from SQL files

Please use `/f` parameter to specify a single SQL file, or use `/d` parameter to specfify a directory that inculdes multiple SQL files.

```shell
java -jar gudusoft.dlineage.jar /t mssql /f path_to_sql_file
```

An xml output will be generated:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<dlineage>
    <process id="9" name="Query Insert-1" procedureName="batchQueries" queryHashId="96cd680daef072c1a4c4b255d830f205" type="sstinsert" coordinate="[1,1,0],[16,37,0]"/>
    <table id="4" name="small_orders" type="table" processIds="9" coordinate="[3,8,0],[3,20,0]">
        <column id="77" name="oid" coordinate="[4,11,0],[4,14,0]"/>
        <column id="78" name="ottl" coordinate="[4,16,0],[4,20,0]"/>
        <column id="79" name="sid" coordinate="[4,22,0],[4,25,0]"/>
        <column id="80" name="cid" coordinate="[4,27,0],[4,30,0]"/>
        <column id="57" name="cl" coordinate="[14,36,0],[14,38,0]"/>
        <column id="58" name="cem" coordinate="[14,53,0],[14,56,0]"/>
        <column id="3" name="RelationRows" coordinate="[3,8,0],[3,20,0]" source="system"/>
    </table>
    <table id="13" name="medium_orders" type="table" processIds="9" coordinate="[6,8,0],[6,21,0]">
        <column id="85" name="oid" coordinate="[7,11,0],[7,14,0]"/>
        <column id="86" name="ottl" coordinate="[7,16,0],[7,20,0]"/>
        <column id="87" name="sid" coordinate="[7,22,0],[7,25,0]"/>
        <column id="88" name="cid" coordinate="[7,27,0],[7,30,0]"/>
        <column id="63" name="cl" coordinate="[14,36,0],[14,38,0]"/>
        <column id="64" name="cem" coordinate="[14,53,0],[14,56,0]"/>
        <column id="12" name="RelationRows" coordinate="[6,8,0],[6,21,0]" source="system"/>
    </table>
    <table id="21" name="large_orders" type="table" processIds="9" coordinate="[9,8,0],[9,20,0]">
        <column id="81" name="oid" coordinate="[10,11,0],[10,14,0]"/>
        <column id="82" name="ottl" coordinate="[10,16,0],[10,20,0]"/>
        <column id="83" name="sid" coordinate="[10,22,0],[10,25,0]"/>
        <column id="84" name="cid" coordinate="[10,27,0],[10,30,0]"/>
        <column id="69" name="cl" coordinate="[14,36,0],[14,38,0]"/>
        <column id="70" name="cem" coordinate="[14,53,0],[14,56,0]"/>
        <column id="20" name="RelationRows" coordinate="[9,8,0],[9,20,0]" source="system"/>
    </table>
    <table id="29" name="special_orders" type="table" processIds="9" coordinate="[12,8,0],[12,22,0]">
        <column id="71" name="oid" coordinate="[13,19,0],[13,22,0]"/>
        <column id="72" name="cid" coordinate="[13,38,0],[13,41,0]"/>
        <column id="73" name="ottl" coordinate="[13,57,0],[13,61,0]"/>
        <column id="74" name="sid" coordinate="[14,16,0],[14,19,0]"/>
        <column id="75" name="cl" coordinate="[14,36,0],[14,38,0]"/>
        <column id="76" name="cem" coordinate="[14,53,0],[14,56,0]"/>
        <column id="28" name="RelationRows" coordinate="[12,8,0],[12,22,0]" source="system"/>
    </table>
    <table id="33" name="orders" alias="o" type="table" coordinate="[15,6,0],[15,14,0]">
        <column id="34" name="order_id" coordinate="[13,8,0],[13,18,0]"/>
        <column id="35" name="customer_id" coordinate="[13,24,0],[13,37,0]"/>
        <column id="36" name="order_total" coordinate="[13,43,0],[13,56,0]"/>
        <column id="37" name="sales_rep_id" coordinate="[14,1,0],[14,15,0]"/>
    </table>
    <table id="41" name="customers" alias="c" type="table" coordinate="[15,16,0],[15,27,0]">
        <column id="42" name="credit_limit" coordinate="[14,21,0],[14,35,0]"/>
        <column id="43" name="cust_email" coordinate="[14,40,0],[14,52,0]"/>
        <column id="44" name="customer_id" coordinate="[16,23,0],[16,36,0]"/>
    </table>
    <resultset id="46" name="INSERT-SELECT-1" type="insert-select" coordinate="[13,8,0],[14,56,0]">
        <column id="47" name="oid" coordinate="[13,8,0],[13,22,0]"/>
        <column id="48" name="cid" coordinate="[13,24,0],[13,41,0]"/>
        <column id="49" name="ottl" coordinate="[13,43,0],[13,61,0]"/>
        <column id="50" name="sid" coordinate="[14,1,0],[14,19,0]"/>
        <column id="51" name="cl" coordinate="[14,21,0],[14,38,0]"/>
        <column id="52" name="cem" coordinate="[14,40,0],[14,56,0]"/>
        <column id="45" name="RelationRows" coordinate="[13,8,0],[14,56,0]" source="system"/>
    </resultset>
    <relationship id="1" type="fdd" effectType="select">
        <target id="47" column="oid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,8,0],[13,22,0]"/>
        <source id="34" column="order_id" parent_id="33" parent_name="orders" parent_alias="o" coordinate="[13,8,0],[13,18,0]"/>
    </relationship>
    <relationship id="2" type="fdd" effectType="select">
        <target id="48" column="cid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,24,0],[13,41,0]"/>
        <source id="35" column="customer_id" parent_id="33" parent_name="orders" parent_alias="o" coordinate="[13,24,0],[13,37,0]"/>
    </relationship>
    <relationship id="3" type="fdd" effectType="select">
        <target id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]"/>
        <source id="36" column="order_total" parent_id="33" parent_name="orders" parent_alias="o" coordinate="[13,43,0],[13,56,0]"/>
    </relationship>
    <relationship id="4" type="fdd" effectType="select">
        <target id="50" column="sid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,1,0],[14,19,0]"/>
        <source id="37" column="sales_rep_id" parent_id="33" parent_name="orders" parent_alias="o" coordinate="[14,1,0],[14,15,0]"/>
    </relationship>
    <relationship id="5" type="fdd" effectType="select">
        <target id="51" column="cl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,21,0],[14,38,0]"/>
        <source id="42" column="credit_limit" parent_id="41" parent_name="customers" parent_alias="c" coordinate="[14,21,0],[14,35,0]"/>
    </relationship>
    <relationship id="6" type="fdd" effectType="select">
        <target id="52" column="cem" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,40,0],[14,56,0]"/>
        <source id="43" column="cust_email" parent_id="41" parent_name="customers" parent_alias="c" coordinate="[14,40,0],[14,52,0]"/>
    </relationship>
    <relationship id="9" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="77" column="oid" parent_id="4" parent_name="small_orders" coordinate="[4,11,0],[4,14,0]"/>
        <source id="47" column="oid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,8,0],[13,22,0]"/>
    </relationship>
    <relationship id="10" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="80" column="cid" parent_id="4" parent_name="small_orders" coordinate="[4,27,0],[4,30,0]"/>
        <source id="48" column="cid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,24,0],[13,41,0]"/>
    </relationship>
    <relationship id="11" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="78" column="ottl" parent_id="4" parent_name="small_orders" coordinate="[4,16,0],[4,20,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]"/>
    </relationship>
    <relationship id="12" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="79" column="sid" parent_id="4" parent_name="small_orders" coordinate="[4,22,0],[4,25,0]"/>
        <source id="50" column="sid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,1,0],[14,19,0]"/>
    </relationship>
    <relationship id="13" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="57" column="cl" parent_id="4" parent_name="small_orders" coordinate="[14,36,0],[14,38,0]"/>
        <source id="51" column="cl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,21,0],[14,38,0]"/>
    </relationship>
    <relationship id="14" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="58" column="cem" parent_id="4" parent_name="small_orders" coordinate="[14,53,0],[14,56,0]"/>
        <source id="52" column="cem" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,40,0],[14,56,0]"/>
    </relationship>
    <relationship id="16" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="85" column="oid" parent_id="13" parent_name="medium_orders" coordinate="[7,11,0],[7,14,0]"/>
        <source id="47" column="oid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,8,0],[13,22,0]"/>
    </relationship>
    <relationship id="17" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="88" column="cid" parent_id="13" parent_name="medium_orders" coordinate="[7,27,0],[7,30,0]"/>
        <source id="48" column="cid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,24,0],[13,41,0]"/>
    </relationship>
    <relationship id="18" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="86" column="ottl" parent_id="13" parent_name="medium_orders" coordinate="[7,16,0],[7,20,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]"/>
    </relationship>
    <relationship id="19" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="87" column="sid" parent_id="13" parent_name="medium_orders" coordinate="[7,22,0],[7,25,0]"/>
        <source id="50" column="sid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,1,0],[14,19,0]"/>
    </relationship>
    <relationship id="20" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="63" column="cl" parent_id="13" parent_name="medium_orders" coordinate="[14,36,0],[14,38,0]"/>
        <source id="51" column="cl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,21,0],[14,38,0]"/>
    </relationship>
    <relationship id="21" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="64" column="cem" parent_id="13" parent_name="medium_orders" coordinate="[14,53,0],[14,56,0]"/>
        <source id="52" column="cem" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,40,0],[14,56,0]"/>
    </relationship>
    <relationship id="23" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="81" column="oid" parent_id="21" parent_name="large_orders" coordinate="[10,11,0],[10,14,0]"/>
        <source id="47" column="oid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,8,0],[13,22,0]"/>
    </relationship>
    <relationship id="24" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="84" column="cid" parent_id="21" parent_name="large_orders" coordinate="[10,27,0],[10,30,0]"/>
        <source id="48" column="cid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,24,0],[13,41,0]"/>
    </relationship>
    <relationship id="25" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="82" column="ottl" parent_id="21" parent_name="large_orders" coordinate="[10,16,0],[10,20,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]"/>
    </relationship>
    <relationship id="26" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="83" column="sid" parent_id="21" parent_name="large_orders" coordinate="[10,22,0],[10,25,0]"/>
        <source id="50" column="sid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,1,0],[14,19,0]"/>
    </relationship>
    <relationship id="27" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="69" column="cl" parent_id="21" parent_name="large_orders" coordinate="[14,36,0],[14,38,0]"/>
        <source id="51" column="cl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,21,0],[14,38,0]"/>
    </relationship>
    <relationship id="28" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="70" column="cem" parent_id="21" parent_name="large_orders" coordinate="[14,53,0],[14,56,0]"/>
        <source id="52" column="cem" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,40,0],[14,56,0]"/>
    </relationship>
    <relationship id="30" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="71" column="oid" parent_id="29" parent_name="special_orders" coordinate="[13,19,0],[13,22,0]"/>
        <source id="47" column="oid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,8,0],[13,22,0]"/>
    </relationship>
    <relationship id="31" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="72" column="cid" parent_id="29" parent_name="special_orders" coordinate="[13,38,0],[13,41,0]"/>
        <source id="48" column="cid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,24,0],[13,41,0]"/>
    </relationship>
    <relationship id="32" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="73" column="ottl" parent_id="29" parent_name="special_orders" coordinate="[13,57,0],[13,61,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]"/>
    </relationship>
    <relationship id="33" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="74" column="sid" parent_id="29" parent_name="special_orders" coordinate="[14,16,0],[14,19,0]"/>
        <source id="50" column="sid" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,1,0],[14,19,0]"/>
    </relationship>
    <relationship id="34" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="75" column="cl" parent_id="29" parent_name="special_orders" coordinate="[14,36,0],[14,38,0]"/>
        <source id="51" column="cl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,21,0],[14,38,0]"/>
    </relationship>
    <relationship id="35" type="fdd" effectType="insert" processId="9" processType="sstinsert">
        <target id="76" column="cem" parent_id="29" parent_name="special_orders" coordinate="[14,53,0],[14,56,0]"/>
        <source id="52" column="cem" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[14,40,0],[14,56,0]"/>
    </relationship>
    <relationship id="7" type="fdr" effectType="select">
        <target id="45" column="RelationRows" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,8,0],[14,56,0]" source="system"/>
        <source id="35" column="customer_id" parent_id="33" parent_name="orders" parent_alias="o" coordinate="[13,24,0],[13,37,0]" clauseType="where"/>
        <source id="44" column="customer_id" parent_id="41" parent_name="customers" parent_alias="c" coordinate="[16,23,0],[16,36,0]" clauseType="where"/>
    </relationship>
    <relationship id="8" type="fdr" effectType="insert">
        <target id="3" column="RelationRows" parent_id="4" parent_name="small_orders" coordinate="[3,8,0],[3,20,0]" source="system"/>
        <source id="45" column="RelationRows" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,8,0],[14,56,0]" source="system"/>
    </relationship>
    <relationship id="15" type="fdr" effectType="insert">
        <target id="12" column="RelationRows" parent_id="13" parent_name="medium_orders" coordinate="[6,8,0],[6,21,0]" source="system"/>
        <source id="45" column="RelationRows" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,8,0],[14,56,0]" source="system"/>
    </relationship>
    <relationship id="22" type="fdr" effectType="insert">
        <target id="20" column="RelationRows" parent_id="21" parent_name="large_orders" coordinate="[9,8,0],[9,20,0]" source="system"/>
        <source id="45" column="RelationRows" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,8,0],[14,56,0]" source="system"/>
    </relationship>
    <relationship id="29" type="fdr" effectType="insert">
        <target id="28" column="RelationRows" parent_id="29" parent_name="special_orders" coordinate="[12,8,0],[12,22,0]" source="system"/>
        <source id="45" column="RelationRows" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,8,0],[14,56,0]" source="system"/>
    </relationship>
    <relationship id="36" type="fdr" effectType="insert">
        <target id="77" column="oid" parent_id="4" parent_name="small_orders" coordinate="[4,11,0],[4,14,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]" clauseType="insertValues"/>
    </relationship>
    <relationship id="37" type="fdr" effectType="insert">
        <target id="78" column="ottl" parent_id="4" parent_name="small_orders" coordinate="[4,16,0],[4,20,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]" clauseType="insertValues"/>
    </relationship>
    <relationship id="38" type="fdr" effectType="insert">
        <target id="79" column="sid" parent_id="4" parent_name="small_orders" coordinate="[4,22,0],[4,25,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]" clauseType="insertValues"/>
    </relationship>
    <relationship id="39" type="fdr" effectType="insert">
        <target id="80" column="cid" parent_id="4" parent_name="small_orders" coordinate="[4,27,0],[4,30,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]" clauseType="insertValues"/>
    </relationship>
    <relationship id="40" type="fdr" effectType="insert">
        <target id="85" column="oid" parent_id="13" parent_name="medium_orders" coordinate="[7,11,0],[7,14,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]" clauseType="insertValues"/>
    </relationship>
    <relationship id="41" type="fdr" effectType="insert">
        <target id="86" column="ottl" parent_id="13" parent_name="medium_orders" coordinate="[7,16,0],[7,20,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]" clauseType="insertValues"/>
    </relationship>
    <relationship id="42" type="fdr" effectType="insert">
        <target id="87" column="sid" parent_id="13" parent_name="medium_orders" coordinate="[7,22,0],[7,25,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]" clauseType="insertValues"/>
    </relationship>
    <relationship id="43" type="fdr" effectType="insert">
        <target id="88" column="cid" parent_id="13" parent_name="medium_orders" coordinate="[7,27,0],[7,30,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]" clauseType="insertValues"/>
    </relationship>
    <relationship id="44" type="fdr" effectType="insert">
        <target id="81" column="oid" parent_id="21" parent_name="large_orders" coordinate="[10,11,0],[10,14,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]" clauseType="insertValues"/>
    </relationship>
    <relationship id="45" type="fdr" effectType="insert">
        <target id="82" column="ottl" parent_id="21" parent_name="large_orders" coordinate="[10,16,0],[10,20,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]" clauseType="insertValues"/>
    </relationship>
    <relationship id="46" type="fdr" effectType="insert">
        <target id="83" column="sid" parent_id="21" parent_name="large_orders" coordinate="[10,22,0],[10,25,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]" clauseType="insertValues"/>
    </relationship>
    <relationship id="47" type="fdr" effectType="insert">
        <target id="84" column="cid" parent_id="21" parent_name="large_orders" coordinate="[10,27,0],[10,30,0]"/>
        <source id="49" column="ottl" parent_id="46" parent_name="INSERT-SELECT-1" coordinate="[13,43,0],[13,61,0]" clauseType="insertValues"/>
    </relationship>
</dlineage>
```



ss
