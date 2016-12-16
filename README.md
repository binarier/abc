# abc

![Alt text](http://g.gravizo.com/g?
  digraph G {
    node [shape="rect"];
    subgraph cluster0  {
        label = "dagger-controller";
        shape=rect;
		dmclient,hwctrl[label="hw-ctrl"];
	};
    subgraph cluster1  {
        label=Ethernet;
        dmserver,dmnode0,dmnode1,dmnode2,dmnode_x;
    }
    dmserver -> dmclient[dir=both, label="UART"];
    dmserver -> {dmnode0, dmnode1, dmnode2, dmnode_x} [dir=both, label=UDP];
    hwctrl -> lcd[label="SPI"];
    hwctrl -> fan[label="PWM"];
    hwctrl -> acpower[label="AC Power 12V"];
  }
)
