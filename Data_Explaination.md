## Request: PortFolio Analysis
  ### Investor has two files contain his historical records of his investment portolio data and benchmark indices data, in the files  
    - snapshot_date : refer to the date of the portfolio records, format as "YYYY-MM-DD" which including all the calendar days, including those days out of trading schedyle;
    - principle : refer to investor's total investment up to this snapshot date
    - total_asset_value : total market value of all the assets in the portfolio
    - 000001.SS : SSE composite Index (CN)
    - 399001.SZ : SZSE composite Index (CN)
    - 00300.SS : CSI 300 Index (CN)
    - ^GSPC : S&P 500 Index (Standard & Pool's 500 Index) (US)
    - ^IXIC : Nasdaq composite Index (US)
    - ^FTSE : Financial Time Stock Exchange 100 Index (UK)
    - ^HSI : Heng Sang Index (HK)
  ### Now the inverstor wants to do performance benchmark and analyze his portfolio
    - Performance benchark: since the investor will invest capital into his portfolio time by time, if simply benchmark between his total asset value and the benchmark indices, the result will be distort by his capital changing over the time, thus a proper method will be treat his portfolio as a fund, let's make a example below:
      - From day one (the first of the snapshot_date), we will consider it as a fund, give him a fix share number, let's say 1,000. then the per share value will be (total asset value)/(total share number), if the total asset value is 1000, then the per share value will be 1.
      - Over the time, the portfolio's market value will be flunctuated along with the market changes, the per share value will be changed, but the formular remain as (total asset value)/(total share number)
      - After a while, the investor will invest some money into the portfolio, let's say one day, he invested additional 200, now what changed? if you treat his portfolio as a fund, his total share will be changed, we will use previous day's per share value as the baseline, his new share number will be 1,000 + 200 /(previous day's per share value), let's say, the per share value is 2 for the previous day, it means his total share will be increased by 200/2=100, thus his total share number will become to 1,000+100=1,100, his principle now is 1,200.
      - Later, he wants to withdraw some money, say 150, at that day, the per share value of previous day change to 1.5 per share, thus mean, the total share of the portfolio become to 1,100 - 150 /1.5 = 1,000, the principle of the portdolio truns to 1,200 - 150 =1,050.
      - now,how we evalue his portfolio's performance by benchmark the portfolio's per share value with the benchmark indices over the time period we selected. It will be reasonable and correctly respect the time value and the dynamic changes of the financial market.
    - For analysis: since we don't have detail information of the portoflio, we can analyze the investor's investing bevaire along with the market changes (by principle changes）, time rolling analysis, risk analysis etc. by per share value changing 




