# DAX
MEDIDAS E PROGRAMAÇÃO EM DAX

#ValorVenda YoY% = # 
 IF(
    ISFILTERED('Tabela Calendario'[Date]),
    VAR __PREV_YEAR =
        CALCULATE(
            SUM('Vendas'[ValorVenda]),
            DATEADD('Tabela Calendario'[Date].[Date], -1, YEAR)
        )
    RETURN
        DIVIDE(SUM('Vendas'[ValorVenda]) - __PREV_YEAR, __PREV_YEAR))
