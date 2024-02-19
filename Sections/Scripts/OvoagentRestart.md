## OVO AGent Restart

**By writing below command in CMD we could restart the OVO agents**

    ovc –kill
    cd "C:\Program Files\HP Openview\data\tmp\OpC"
    del *p *q
    cd "C:\Program Files\HP Openview\data\tmp\public\OpC"
    del *p *q
    ovc –start
    opcagt –cleanstart
