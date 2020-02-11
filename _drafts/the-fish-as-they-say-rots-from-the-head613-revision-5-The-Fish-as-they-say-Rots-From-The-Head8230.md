---
id: 618
title: 'The Fish, as they say, Rots From The Head&#8230;'
date: 2009-02-14T06:42:52+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/613-revision-5/
permalink: /gruedorf/613-revision-5/
---
### Back in 2004 I wrote

_I do not give a shit if you&#8217;re a republican, nor a democrat. If you think the system as it is is shitty, and you&#8217;re not in a battleground state, and you didn&#8217;t vote third party, then you&#8217;re a non-sentient hypocrite nimrod whom I have no respect, intellectual or otherwise, for._

Nobody understood this properly when I wrote it originally, so then in my comments I wrote some psuedocide to explain the logic flow of that sentence and it cleared it up.

(Aside: Comparison of the previous two sentences shows that in five years I&#8217;ve not stopped ending my sentence in prepositions. I, like most of you, run english in quirks mode.)

### The conclusion

Code is far less ambiguous than english because people are not used to strictly interpreting english. (The previous sentence implies that math majors are not people; I&#8217;m willing to defend that.)

So I revisited the psuedocode in the post and found it amazingly brittle and unreusable! And there was a bug in the final clause. Oh, the perils of not test-driving your emotionally charged statements. So, in the interests of avoiding arrogance-rot, I refactored and generalized it a bit!

### An Exemption

I&#8217;m not sure if I believe this anymore at all. It&#8217;s been a while since I re-evaluated my political stances. I think I&#8217;ve gone from a hardline libertarian to a broken, beaten, shattered shell of a libertarian. So, the contentious arguments here aren&#8217;t so applicable anymore. I just wanted to point illustrate that the opening statement is hyper-charged and people fail to interpret it correctly, whereas the code is much easier to interpret to those who have been trained in the Way of the Computer.

<pre style="width: 510px; padding: 20px;  background-color: #efefef; line-height:125%;" >/// Takes a Person object, and sets it's member variables accordingly for
/// it's 1::1 relation with Grue in respect to Grue's respect for that
/// Person.
/// 
/// @param you The person to judge.
/// @see Person::ProcessReaction()
/// @see _BattlegroundStateCalculator()
/// @todo implement all of the various non-election-related ways a person
///       can be a total douche in my eyes.
/// @todo exemption clauses for 'lesser of two evils'?
/// @todo set dead_to_me flag if '3rd party'/'wasted vote' argument comes
///       up.
void Grue::CalculateRespect( Person you )
{

    PoliticalOffice* p_office;
    p_office = PoliticalService.getCurrentOfficeUpForGrabs();
    
    if( 
        // if you think the current system is Shitty...
        you.opinion_on_US_govt == E_FUNDAMENTALLY_FLAWED &&

        // ...and if you *dont* live in a battleground state...
        // (calls a helper function)
        !_BattlegroundStateCalculator(you.state_of_residence) &&
        
        ( 
          you.vote[TimeService.getCurYear()][p_office] == 
              PoliticalService.getCandidateForOffice(p_office,'GOP') 
          || 
          you.vote[TimeService.getCurYear()][p_office] == 
              PoliticalService.getCandidateForOffice(p_office,'DNC') 
        )    
    ) {
        you.hypocrite = true;
        you.sentient = false;

        // set all possible forms of respect as false.
        for( int i=0; i&lt;MAX_RESPECT; i++ )
            you.grue_respect[i] = false;    
    }
    else // only do this if they were not deemed Horrible.
    {
    
        // Now see if the person was offended by the process we just judged 
        // them against...
        you.ProcessReaction();

        // if somehow you're offended during this evaluation for any reason,
        // mainly for not understanding the hierarchy of judgement, then 
        // you're dumbstuffs for being offended, but I cannot judge you
        // otherwise.
        if( you.offended_flag ) 
        {
            you.grue_respect[i] = REPECT_INTELLECTUALLY;
        }
    }
} //Grue::CalculateRespect()
</pre>