---
layout: hyrban
title: Notes on licensing April 2020
date: 2022-06-10
description: TODO-description
---
%%(width:750px;)
###Intro

The licensing regime is critical to the success of any open source project. There is an on-going debate amongst those running 40 Fires as to what regime to put in place. We are breaking new ground. A Word document is attached, which you can download by clicking on the Attach label above. or read it below. And to join the discussion, the forum is embedded at the bottom of this page:

###Summary

Our vision is of a world where the technology to produce low carbon, sustainable vehicles is shared freely. 

Our task is to create a legal and economic system to encourage cooperation and trade in such technology.  

Our assumption has to be that people are in general rational, and respond to incentives. So that if we can create a framework within which, for most people, the advantages of adhering to the norms of behaviour of the community are greater than the advantages of not adhering, we will create a sustainable community and achieve our aims. 

###Some basic principles

- There must be low barriers to entry (although there may be higher barriers where the rewards for participating are high).

- Participants should have considerable flexibility in how they engage with the community. 

- Riversimple is to be treated symmetrically to other manufacturers. 

###Some observations

- __40 Fires/Riversimple__  When considering what legal and economic structure to devise, we need to bear in mind the broad aims of 40 Fires and not just those of the participants such as founder Riversimple LLP.  

Having said that, it would be self-defeating to devise a strategy which does not serve Riversimple's needs, since Riversimple is a key (at present, the key) member of the 40 fires community and is currently the sole source of funding for 40 Fires. It is reasonable to assume that the main contributors (but by no means the only contributors) to 40 Fires will be commercial organisations, including car manufacturers such as Riversimple and component manufacturers and integrators. If we don't allow these businesses to make money, 40 Fires will not achieve its aims.  

- __Riversimple’s aims__  For additional context, it is worth remembering the commercial aims of Riversimple in initiating the 40 Fires Foundation (ignoring for this purpose any broader aims that the founders of Riversimple may have). These are to:
	
-	drive the adoption of common standards for hydrogen fuel cell powered vehicles; 
-	reduce the costs of development of its products; 
-	improve the quality of the products; and
-	kick-start the age of truly energy efficient and sustainable vehicles, in which Riversimple aims to be a key player. 

- __40 Fires vehicles and Riversimple vehicles__  We envisage a broad class of 40 Fires vehicles (similar perhaps to the “PC” class of personal computers) and within that class will be cars made by Riversimple and others (analogous to Dell, Toshiba and Asus who all make PCs). 40 Fires cars will differentiate themselves from other classes of cars by their energy-efficiency, robustness, ease of service and minimalist design approach to the working parts.  Riversimple would expect to differentiate themselves from other 40 Fires cars through styling and by the high level of customer service. 

- __A car of many parts__.  A car is a complex machine. In order to create a car, you need to:
	- modify existing software (which may be subject to a license);
	- create new software (which can be protected by copyright);
- design mechanical and electronic hardware (which can be protected from copying only by patents) – this hardware may include embedded software, which may be subject to a license; 
- integrate a number of third party components, which may include both software and hardware.   
- create a look for the car bodyshell and other visible parts, the so-called 	styling (this can be protected through design rights);
- develop know-how in manufacturing, assembling, servicing and marketing the vehicle (this can be protected only by confidentiality agreements). 


In summary: 

Software:	   Protected by Copyright

Hardware:	   Protected by Patents

Styling:	   Protected by Design rights

Know-how: 	   Protected by Confidentiality

What implications does this have for licensing?  It means that our licensing regime must deal with each type of creative work.  

Do we require different licenses for different components? 40 Fires could conceivably have one licence that covers copyright, patents and design rights, whilst manufacturers such as Riversimple would protect their own designs and know-how through design rights or contract, respectively.

- __Types of license__.  A key decision is whether 40 Fires should adopt an “academic” license, where people have considerable choice whether to cooperate or not, or a “reciprocal” license where licensees are obliged to apply the same license terms to any distribution (which effectively means they have to share their IP). 

- __Hardware is not software.__   Copyright is an imperfect tool for hardware and/or hardware design documents. It is worth quoting a statement here from one of the creators of the TAPR Open Hardware License (OHL), John Ackerman, in a discussion to be found at [http://technocrat.net/d/2007/2/5/14355]. The discussion relates to computer hardware, but similar principles apply.  

“The GPL operates purely as a copyright license. Pure copyright doesn't work very well for protecting hardware designs because copyright can only protect the expression of an idea, and not the idea itself.  So, the copyright in a schematic diagram is "thin" in that it is highly functional and there are only a limited number of ways in which the components can interconnect.  In other words, someone can take my schematic and use the idea -- that U1 pin 1 connects to U2 pin 3 -- to quite easily recreate that schematic without infringing my copyright.  And, once I have a schematic it's not that big a deal these days to recreate the PCB and get around any copyright in the original artwork. The OHL uses the mutual grant of patent immunities as the legal "consideration" necessary to create a binding contract, and it operates on a contract rather than license theory.  While this isn't perfect, we believe that it provides a more enforceable way to control how Documentation is used than a pure copyright model could. We use an "immunity from suit" rather than a patent license because the immunity is like a quitclaim deed for property -- it says "to the extent I have any rights, I won't use them against you" without making any claim that I actually have those rights.”

- __The GPL (General Public License).__   Although the GPL has been amazingly successful (indeed it is hard to imagine open source without it) there are reasons to question its usefulness for 40 Fires purposes. Leaving aside the issues mentioned above about copyright and hardware, there is the question of what makes a derivative work. Does linking two components together make the resultant work a derivative work? If so, you have to reveal the source code to the whole lot. And the GPL requires you to make distributions of derivative works subject to the GPL. As a result, people have “an unreasonable fear of infection”  from the GPL because they fear it will show up in their ecosystem uninvited. And there is the question of compatibility – the two components may be subject to two different licenses. See also Andrew Katz  thoughts under “the free rider problem” below. 

- __Allowing the use of different licenses.__ The optimum solution may be to give the contributor a choice of licenses to apply to his work. Some participants will want to share all their knowledge openly, some will want to keep certain bits of information for themselves. If we insist on applying one approach (say copyleft), even though it is hard to enforce and complex for many to implement, we may simply turn away potentially valuable participants.   

Some Andrew Katz thoughts: 

“Different parts of the blueprint may be available under different licences. This is entirely consistent with the GNU philosophy: some GNU components are available only under the GPL, and some are available under the LGPL, for example function libraries. Richard Stallman realised that it was better for the freedom of software as a whole if some function libraries were available under a licence which did not require the software which used them to be released under the GPL. This is because there are proprietary function libraries available which contain similar functions, and users wanting to develop proprietary software would find it easy to choose one of the proprietary libraries. Since they were going to produce proprietary software anyway, they might as well be using free software libraries (and getting used to their power and functionality, and, if they make any amendments to that library to release those changes to the community at large). 

Therefore, at the outset of any part of the project, it's important to determine what sort of licence should be applicable to that project. Ignoring for a moment the hardware copyleft problem, this may be a strong copyleft licence (requiring any development which is based on or incorporates the 40Fires invention to itself be licensed under the same licence); or it may be a weak copyleft licence, which only impacts on that invention itself. I have to say, determining what is impacted and what isn't is hugely difficult in the software world, and I think it has to be even more difficult in the hardware world. There is also the option to release under an even less restrictive licence (like the BSD).”

- __Dual licensing.__  It is noteworthy that some projects, notably MySQL, and the QT project sponsored by TrollTech, are released under dual licenses, where the GPL applies when these tools are used in open source projects, and a stricter license applies where they are employed for commercial gain. I am not sure how such a strategy might serve us, but it may be an option to explore. 

- __Royalty or not.__  Another key decision is whether 40 Fires should charge a royalty (or license) fee or find some other way to fund itself. Here are Andrew Katz’s words on this subject: 

“Royalties are a tax on the dissemination of information. If we truly want to this to be an free/open source company, we never want to compromise the ability for information to be disseminated freely, and free of charge. Instead, 40Fires is a service company. Revenues are derived from consultancy. Do not underestimate the extent that revenues can be derived from service provision. Red Hat's revenues exceed $500m and it is purely an open source service company. It collects zero royalties.

If 40Fires starts to collect royalties, this will be viewed negatively by the community. To try to describe 40Fires as a company adopting open source principles (without being properly open source) is disingenuous at best, and will lose a significant amount of goodwill.”

Our aim is to create a structure which gives participants an incentive to share and cooperate. A royalty may have the opposite effect, even if it is a relatively small amount by comparison with the value of a car.   

There is also the question about how much to charge component manufacturers. It is straightforward to charge a royalty fee per car, but what do you charge for individual components? It doesn't seem right to charge nothing, but next to impossible to determine a fair rate for each component. 

There are other ways in which 40 Fires can fund itself perfectly satisfactorily. Andrew Katz again: “As I see it, 40Fires will monetise itself in a similar way to the Mozilla Foundation, and the Open Invention Network, in that it will provide
expertise and consultancy, and accept donations from member companies to
carry out specific tasks. For example, Ford may ask 40Fires to create a
particular suspension geometry for its bodyshell. This would be available to anyone on a royalty free basis, but would be most of use to Ford, so Ford would be prepared to pay. This is exactly how Canonical, for example, works with partners who want a specific version of Ubuntu developed for their hardware (like a netbook). Since there is consultancy work available, this also means the 40Fires has money to pay engineers and developers and other creatives to work for them on specific projects, which is what starts to create the community.” 

- __On patents.__ 40 Fires should “release early, release often”, which would be consistent with open source principles, and would also have the effect of making it more difficult for people to file patents on the released information. 

40 Fires should also aim to register patents. After all, other individuals and businesses will. The possession of patents in a common pool can be useful as a deterrent against litigation. There are several organisations that do this in the field of computing to protect open source enterprises from hostile litigation in an industry where, as Bruce Perens  suggests, "there are simply so many software patents, on so many fundamental principles, that no non-trivial software program could exist that was licensed by all patent holders with claims reading on the algorithms used. This is regardless of whether it is proprietary or free software."

Andrew Katz suggests that 40 Fires set up “a patent structure very similar to the Open Invention Network (and indeed, also joining the Open Invention Network, which could be achieved as a licensee at low or zero cost). This means that under the 40Fires patent structure, anyone holding patents who signs up to it, pledges not to enforce those patents against anyone creating a Hyrban car, and in return, they get a similar pledge from the other members. Use outside the Hyrban context is not restricted (this causes a bit of a problem with the GPL, but that's an issue we can discuss another time). Anyone can sign up to be a licensee under the patents.” Andrew adds that that OIN only covers implementations of Linux but that it is more than likely we will end up with an implementation of Linux somewhere in the car.”

- __Crash test results.__  Crash testing is one area of car development that is clearly and markedly different from software or from low cost hardware. Crash testing is expensive.  Thus our system must enable a manufacturer who undertakes crash testing to either:

		- keep the results to itself, for long enough to give it a head start 		over others who might use the test results; or
		- make the results available in a way that serve their interests; 		for example by charging a fee. 

Clearly the system will benefit if manufacturers can be encouraged to share test results. 

- __Current license arrangements.__ Currently data available for download on the site is subject to a Creative Commons license attribution non-commercial 3.0 See http://creativecommons.org/licenses/by-nc/3.0/. This permits the licensees to adapt, copy, distribute and transmit the work that requires them to attribute the work and prevents them from using the data for commercial purposes. The intention is that if somebody wants to use the data for commercial purposes, they should speak to us first. 

This is probably too cautious an approach, and would not encourage commercial businesses to participate in the community. It has already been the subject of criticism from open source purists.  

- __Riversimple’s worst fear - the Free Rider problem__. The worst fear for Riversimple is that it releases information that a better funded, more politically powerful and more ruthless competitor takes and uses for its own purpose, getting ahead of Riversimple in the race to be first to market yet producing a vehicle that is less efficient and less sustainable. To avoid this, which would clearly have a detrimental effect on 40 Fires, we have previously emphasised the need to apply the copyleft  principle. If the competitor is forced to share the work it derives from 40 Fires, everyone will benefit. 
 
The counter-argument to applying a strong, GPL-like copyleft approach is that it will put many potential contributors off, because of the fears mentioned earlier that they will have to disclose all their knowledge to the community and thus lose any competitive advantage. This was the point well made by Jonathan May in our meeting of 13th April 2010. 

There is also the point that there are many advantages of working with a community – improvements to the products, connection with skilled people who are a pool of potential staff, access to information on latest developments from around the world. Businesses ought to value these enough to be willing to share, without needing the threat of a lawsuit.  

Andrew Katz believes the fear of free riders, in the software world at least, is “very exaggerated. In practice, there are plenty of successful projects (FreeNAS, Apache) which do not rely on strong copyleft to support them, and thrive despite there being “free riders”. We need to consider this further, but members of the Apache community are resistant to the idea of strong copyleft, because of licence incompatibilities between projects, because, the “viral” nature (which admittedly is largely imagined) scares off potential adopters, and because it makes the whole licensing structure very complex. Having said that, it may be dangerous to assume that what works in a software world, will translate to the world of hardware.”

###My tentative conclusions

40 Fires should opt for an “academic” license similar to the BSD, allowing licensees to redistribute data with only limited restrictions, and no obligation to share. At the same time, we would highlight the benefits of sharing data with the community and that 40 Fires has been established with the intention of encouraging sharing to the maximum extent, consistent with commercial success for those participants who need to make a living from their participation. 

We should consider requiring attribution of 40 Fires in the license. 

40 Fires should charge no royalty but rather seek funds through a combination of voluntary contributions or sponsorship from business members of the community, as well (possibly) as providing consulting services. 

Crash test results don't have to be shared, but the manufacture can choose to share them with other community members in return for a fee. 

40 Fires would aim to accumulate patents, which could serve mainly as a defence mechanism against attacks by other patent holders.  

Individual members of the community shall be free to enter into close collaborations with other members, sharing more information than they do in public through the 40 Fires platform. 

We should change the licence under which data is currently made available and permit commercial usage of the data currently available on the site. 

Conclusion

I look forward to receiving comments and other constructive feedback on these thoughts! (For more on this, go to [this|further license notes - 27 April 2010] page). 


DISCUSS HERE:
[{MungeHTML MungeID='nabblelink' reference='f3944671' name='2.1 Licensing' plainName='2.1 Licensing '}]

%%
