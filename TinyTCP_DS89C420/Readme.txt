                    TinyTCP, Embedded TCP/IP Protocol Suite

                     Dallas DS89C420(8051 Compatible) Port
			    for the Keil C Compiler



Acknowledgements
----------------

Most files in this TinyTCP is based on the Dallas DS89C420(8051 Compatible)
for the Keil C Compiler by TechiZ.

The TinyTCP source is available at 
http://www.csonline.net/bpaddock/tinytcp/default.htm

The TinyTCP port for the Dallas DS89C420(8051 Compatible) is available at
http://www.techiz.com/

Hi everyone.

This program was written in Korean(Comment and some more). 

This program was developed by TechiZ(The Company name).
TechiZ want to share this program with you who loves the 8051 & the TCP/IP.

You DO NOT USE THIS CODE FOR COMMERCIAL PURPOSE.
This code is ONLY FREE FOR THE STUDY. If you want more, send me the mail.

E-mail: techiz@techiz.com
( Subject is : [DS89C420 & TinyTCP] bla~ bla bla.... )

You DO NOT DELETE BELOW THE COPYRIGHT MESSAGE IN THE USING OF THIS CODE.

/*
 * Copyright (C) 2002 by TechiZ. All rights reserved.
 *
 * This program was written in Korean(Comment and some more). 
 *
 * This program was developed by TechiZ(The Company name).
 * TechiZ want to share this program with you who loves the 8051 & the TCP/IP.
 * 
 * You DO NOT USE THIS CODE FOR COMMERCIAL PURPOSE.
 * This code is ONLY FREE FOR THE STUDY. 
 * If you want more, send me E-mail.
 *
 * E-mail: techiz@techiz.com
 * ( Subject is : [DS89C420 & TinyTCP] bla~ bla bla.... )
 *
 * Homepage: http://www.techiz.com
 * 
 * You DO NOT DELETE THIS COPYRIGHT MESSAGE IN THE USING OF THIS CODE.
 *
 * In the using of this code, TechiZ does NOT GUARANTEE ABOUT WORKING WITHOUT ERROR.
 */

In the using of this code, TechiZ does NOT GUARANTEE ABOUT WORKING WITHOUT ERROR.

Below sentenses are not translated yet...  it's not a important information but
only bug repair. I don't know this source have any bug. If you found it, let me know..



REPORTING PROBLEMS
------------------

If you find a bug in this port, DO NOT hesitate to report the problem to me
(Gwang-Hyuk, Ahn.):

1) Through E-mail: techiz@techiz.com
( Subject is : [DS89C420 & TinyTCP] bla~ bla bla.... )

2) Use Q&A Board in www.techiz.com(Open Src menu, about 8051)
( Subject is : [DS89C420 & TinyTCP] bla~ bla bla.... )

Make sure that the problem you are reporting is in this port and not in your
application.

Enjoy!!



Hardware
--------
ROM : 0 - 0x7FFF
RAM : 0x8000 - 0xffff
RTL8019AS(Ethernet chip) : ROM area(base = 0x300)



Software
--------
Monitor program : downloadable and executable (from 0x8000) 
// We only use 4M ROM emulator which was made by comrade.
TinyTCP program ( it was repaired to port 8051. Original code is remarked as '// '.)
Ethernet Driver(RTL8019AS)



-------------------------------------------------------------------------------------
Korean Language Add-On ( We are so sorry about add-on,
                         We will translate later if many people want...  ^^;;  )

���� ��Ŷ�� ������ ���� ������ �߳׿�...

1. ���׶��... ���ӵ� ��Ŷ�� 4�� �Ǵ� 5���� ������ ���α׷��� ��������׿�.. -,.-

2. ������ �ణ�� ���׸� ������ä , �׳� ��Ŷ�� �������� �ϴµ���. ���� ���ͷ�Ʈ �κп���
   �ɸ��� ���� ����� �����ϴ�. �ӳĸ� ���� �����Ϸ��� ���ͷ�Ʈ ���͸� 0003(�������)�� 
   �����ϱ� ������ ��ó�� ��(8000h)�� �ٿ�ε��Ͽ� �����ϴ� ���� ������ �ȵȴ�.
   �Ƹ��� startup�κп��� �ذ��ؾ� �� ���̴�. ����� �Ƹ�Ű�޵��� �����Ϸ������� ���ͷ�Ʈ
   �κп��� �ƹ� �̻��� �����µ�    .  ��.�� �ָ���..

5. ���ͷ�Ʈ �κ� �׽�Ʈ���� �Դϴ�. ������ ���ͷ�Ʈ�� ��������� ���������� ��ġ�ϱ� ������
   Ȱ���� �Ϸ��� �ҿ��Ŀ��� ����ְ� �ϴ� ����� ���� ���� �� ���׿�. �׸��� �ҽ����� ��������
   �κ��� DMA_read �κ��ε�, ���⿡ ���õ� byte *buf�� �����ϸ� �����Ͽ� ������ �����ϴ�.


6. 2000.11.12 : ���ͷ�Ʈ�� ���� �̻��ϴ�. RTL8019AS�� IMR�� ISR�� ��Ȯ�� ���踦 �𸣰ڴ�.
   ���� ��� IMR�� ����ũ���� �ʾƵ� ���ͷ�Ʈ�� �߻��ߴ�.. �׷��� ���� IMR�� ������ 0x01�� �ߴ�.

7. 2000.11.16 DoS�� ����Ϸ��� ������ �Ȱ��� ��Ŷ�� ������ ��, �ʹ� ������ �����ϸ� ���尡 ����
   ������. ��¿ ���� �� ���߰� �� ������ ������, �ƹ��� delay���� ���۵Ǹ� �ٷ� �ٿ�ȴ�.

8. �ʱ�ȭ�� �߸��ؼ� �۽��� ���� �ȵǾ���. �Ʒ� �ҽ��� ���� �ҽ����� ���̸� ��Ÿ�� �κ��̴�. 
   ���� ������ �ȵǴ� �ҽ��̴�. �� �׷����� ���� �𸣰ڴ�. �ᱹ���� ������ ��� �ҽ��� ī���ؼ�
   ����ߴ�. 
	EN_CMD = EN_NODMA + EN_PAGE0 +  EN_STOP;  /* 00001010B: 
	EN0_ISR = 0x00;
	EN0_ISR = 0xff; 	
    					
	EN0_IMR = ENISR_ALL; 

	EN_CMD = EN_NODMA + EN_PAGE3 + EN_STOP;
	//CONFIG1 = 0x90;   
	//CONFIG2 = 0x20;
	//CONFIG3 = 0xf0;
	
	CONFIG1 = 0x90;  
	CONFIG2 = 0x00;
	CONFIG3 = 0xf0;
	CONFIG4 = 0x00;
	
	EN_CMD = EN_NODMA + EN_PAGE3 + EN_STOP;
	EN0_TXCR = ENTXCR_TXCONFIG;     
   
	EN0_RXCR = ENRXCR_RXCONFIG;      
	
	EN_CMD = EN_NODMA + EN_PAGE3 + EN_START;
	EthRxBufRdPtr = 0;
	EthRxBufWrPtr = EthRxBufRdPtr + 1;

9. ei_rx_overrun �Լ����� ������ ����
	if (was_txing) { 
		if (!(EN0_ISR & (ENISR_TX + ENISR_TX_ERR))) must_resend = 1;
   	}
    �ٲپ�� �Ѵ�. �׸��� ���÷� isr_all �κ��� �����ϱ� �ٶ���.

10. ��ġ�� Ÿ�̸�0 ����ϰ� ����ϰ� �־ ������ �κ��� �ƽθ� �ʱ�ȭ�� ��Ű�� �ֱ���...
    ������ �� ������, �ø����� ���ͷ�Ʈ�� ���� ��ƾ���� ���ÿ� ���� ���尡 ���� �����ϴ�.
    �� �κ��� �ø��� ���ͷ�Ʈ�� �����۸� ����Ͽ� �ذ��� �����̰�, ��....  ���� ��Ŷ�� ������
    ����� �����ߴٸ� �� ���� ������ tinytcp���� ������ Ȯ���� �ϴ� �͸� ���ҽ��ϴ�.

11. inportb & outportb�� �������͸� �׼����ϸ� �̻��� ���� ���δ�. !!!!
    ���� ���� ����̹��μ� ������ �ϴ°� ����. �Ѱ��� �̻��� ���� ���� ���δ�. �Ƹ��� inytcp�� 
    ������ �Ŀ� �� �κ� �����̴�.

12. ���� 22.1184Mhz�� �ӵ����� 8Khz�� timer interrupt�� �ɷȴٰ� �����ϰ� ethernet 
    ����̹��� ¥�� �ִ�. ������ �ӵ����� ����� ������ �ִ�. �켱 �ʴ� 8000���� ����Ÿ��
    ��Ʈ��ũ�� �������� ��Ŷ�� �ִ� 1500����Ʈ, �� 8000/1500 = 5.3 �׷��ϱ� �ƹ� ������
    ���� 6���� ��Ŷ�� �����ٸ� ��������Ÿ�� ��Ȯ�� ������ �� �ִ�. ������ 6���� ��Ŷ�� 
    �ޱ⵵ �ؾ��ϱ� ������ ������ �� ���� ����.

13. ���ͷ�Ʈ ���Ͽ� ���� Ŭ���̾�Ʈ ���α׷�(ADUC.C)�� ����Ǿ�� �Ѵ�. ������ ��� ����
    ���μ��������� usleep(number)�� �÷��� �ʿ䰡 �ִ�. �׷��� ���� ������ ��� ��Ŷ�� 
    �޴ٰ� ������.
14. IE�� �����Ͽ�(0x87) adpcm�� �����ϸ� ethernet�� ������ ���� �ʴ´�. ��ƾ�߿���
    EA = 0; ���� ����� �ִ� �κ��� �ִµ�, �Ƹ��� �����ؾ� �ɰ� ����.

15. drv_8019.c ���� byte loop�� word loop�� �ٲپ���. ���� �̷��� ���� ������ 255���ڰ� �Ѵ�
    ����Ÿ�� ���ؼ��� ������ �ϸ��� ���尡 ���� ���̴�.
    
16. ���ݱ����� arp�� ������ �����Ͽ� ����Ͽ���. �����ϰ� -_-;   
    Cygwin����  : arp -s 202.30.20.172 12-34-56-78-9a-bc
    Linux ����  : arp -s 202.30.20.172 123456789abc
    �̷�������� root�� ������ �� ����Ͽ���. ������ �������ʹ� �׷� �ʿ䰡 ����. 
    ���׸� ������ϱ�..   ��������, �Ʒ��� ���� 2�������� �Ͽ���. �ᱹ���� 0�� �������
    ����� �Ǵϱ� �ȵ� �� �ۿ�..  �׷��� �Ʒ����� ����ų� �ּ�ó���ؾ��Ѵ�. 
    
    EN0_RXCR = ENRXCR_RXCONFIG;      /* rx on(broadcasts, no multicast,errors */
    //EN0_RXCR = 0;      /* rx on(broadcasts, no multicast,errors */ 

17. �ѹ� ���� ���α׷��� ������ �Ǹ� broadcat�� disable���Ѽ� �ӵ��� ����Ŵ
    tinymain.c�� WORD test_application( void )�� �߰���Ŵ.

18. hdr[3]�̶�� �Ǿ� �ִºκ��� [4]���ľ��Ѵ�.