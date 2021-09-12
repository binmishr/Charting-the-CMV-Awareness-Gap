# Charting-the-CMV-Awareness-Gap

The details of the codeset and plots are included in the attached Adobe Acrobat reader (.pdf) file in this repository. 
You need to download the same to view the contents. There are referrals to other contents in BLUE colour also to follow.


Introduction

Speaking of viruses, did you know that June is National Cytomegalovirus
(CMV) Awareness Month?
Probably not, since most people have never heard of CMV (hence the need
for a national awareness month).

CMV is a common virus that infects 50-80% of people by the time they are
40 years old. In most cases, it’s not a big deal. But if a pregnant
woman becomes infected, she can pass the virus to the unborn child,
which results in a congenital infection about 33% of the time.

Congenital CMV (cCMV) is the number one viral cause of birth defects in
children. According to National CMV
Foundation, 1 in 200 children
are born with CMV every year. That’s roughly 30,000 children. About 1 in
5 children born with CMV infection will have moderate to severe health
problems including:

    Hearing loss
    Vision loss
    Feeding issues
    Intellectual disability
    Microcephaly (small head or brain)
    Cerebral Palsy
    Seizures

Outcomes associated
with congenital CMV are wide-ranging and unpredictable.

Despite how common and potentially damaging CMV is, research shows that
only 9% of women have heard of the condition.
Awareness = prevention

Because cCMV is a viral infection, it is potentially preventable during
pregnancy if you know to take certain basic
precautions.However, knowing to take precations requires having heard of the
condition in the first place, which brings us back to the need for a
National CMV Awareness Month.

One of the main tactics used in CMV awareness raising efforts is to
highlight the “awareness gap” between how few women have heard of CMV
and how many children are disabled by the condition each year.

In the past, the National CMV Foundation has used the graphic below for
this purpose (Fig. 1). It nicely shows levels of awareness vs incidence
of various congenital conditions in the US, based on data from Doutre
et al. (2016).

![image](https://user-images.githubusercontent.com/26252963/132973631-3f04d18f-43b4-4868-bcf7-d72d150514a0.png)



Recently, I was asked by the Foundation to revise this graphic to
enhance its effectiveness (not coincidentally, my
wife is the Chair of the Scientific
Advisory Committee).

In this post, I describe my approach using
ggplot2, as well as
cowplot and
related pacakges in R.
Mind the gap

Technically speaking, Fig. 1 is what you would call a bi-directional,
mirrored, diverging, or back-to-back bar chart. It is reminiscent of
pyramid style bar charts often used to visualize population age distributions.

I suspect that when people see Fig. 1 they have a perceptual tendency to
sum the bars together rather than take the difference between each bar.
The former is typically how a bi-directional bar chart would be
interpreted. But since the purpose of the visualization is to highlight
the CMV awareness gap, it might be better to actually plot the gap
(linear distance) between awareness and incidence of long-term health problems for cCMV in comparison
to other conditions.

So my proposed enhancement is to layer the incidence data as a series of
dots on top of an ordered bar chart representing increasing awareness on
the x-axis, and use a secondary x-axis for incidence. Layering in this
way will create a visually salient gap between awareness and incidence
for cCMV at the top of the chart, which I can further highlight with
some text annotations.
Secondary axis (of evil?)

However, more recent versions of the package have included this
functionality with the sec_axis() function described
here. I think we can assume from the addition of this functionality that Hadley isn’t
completely averse to the use of a secondary axis in some situations when
used with caution.

![image](https://user-images.githubusercontent.com/26252963/132973647-45e2390d-40f3-45bf-a5ce-b62faf35ba65.png)


Again, my rationale for using a secondary x-axis in this case is to
achieve a specific perceptual effect, to higlight the gap between cCMV
awareness and incidence of disability visually so that people viewing the chart will
say “Wow! That’s some big gap.” And I think I can achieve this without
being manipulative or misleading, becuase the gap really is quite big.
