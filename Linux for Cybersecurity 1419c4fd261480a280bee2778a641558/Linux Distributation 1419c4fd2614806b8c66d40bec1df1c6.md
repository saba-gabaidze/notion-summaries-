# Linux Distributation

![image.png](Linux%20Distributation%201419c4fd2614806b8c66d40bec1df1c6/image.png)

# **RHEL**

**(Red Hat Enterprise Linux)**

The main, stable version used by businesses and large organizations. It's built for enterprise environments with long-term support and security.

## Key facts

Some of the key facts about the Red Hat distribution family are:

- Fedora serves as an upstream testing platform for RHEL.
- CentOS is a close clone of RHEL; in fact, CentOS has been part of Red Hat since 2014.
- A heavily patched version 4.18 kernel is used in RHEL/CentOS 8 Stream, while version 5.14 is used in RHEL/CentOS 9 Stream.
- It supports multiple hardware platforms.
- It uses dnf, the RPM-based package manager (covered in detail later) to install, update, and remove packages in the system.
- RHEL is widely used by enterprises which host their own system

## **Fedora**

 A community-driven version that's closely related to RHEL but includes more cutting-edge software. It's often used to test new features that will eventually be included in RHEL. Fedora gets updated every 6 months.

## **CentOS**

 This version is nearly identical to RHEL but was free to use. However, **CentOS 8** stopped getting updates after 2021. Instead, **CentOS Stream** was introduced as its replacement. The difference is that **CentOS Stream** gets updates *before* RHEL, while the old CentOS version got updates *after* RHEL.

# **The SUSE Family**

The relationship between SUSE  (SUSE Linux Enterprise Server, or SLES) and openSUSE is similar to the one described between RHEL, CentOS, and Fedora.

![](https://courses.edx.org/asset-v1:LinuxFoundationX+LFS101x+1T2023+type@asset+block/LFS101x_2023_CourseImages_1-5_Image_3.png)

We use openSUSE as the reference distribution for the SUSE family, as it is available to end users at no cost. Because the two products are extremely similar, the material that covers openSUSE can typically be applied to SLES with few problems.

## Some of the key facts about the SUSE family are listed below

- SUSE Linux Enterprise Server (SLES) is upstream for openSUSE.
- Kernel version 5.14 is used in openSUSE Leap 15.4.
- It uses the RPM-based zypper package manager (we cover it in detail later) to install, update, and remove packages in the system.
- It includes the YaST (Yet Another Setup Tool) application for system administration purposes.
- SLES is widely used in retail and many other sectors.

# **The Debian Family**

The Debian distribution is upstream for several other distributions, including Ubuntu. In turn, Ubuntu is upstream for Linux Mint and a number of other distributions. It is commonly used on both servers and desktop computers. Debian is a pure open source community project (not owned by any corporation) and has a strong focus on stability.

Debian provides by far the largest and most complete software repository to its users of any Linux distribution.

![](https://courses.edx.org/asset-v1:LinuxFoundationX+LFS101x+1T2023+type@asset+block@LFS101x_2023_CourseImages_1-5_Image_4.png)

Ubuntu aims at providing a good compromise between long term stability and ease of use. Since Ubuntu gets most of its packages from Debian’s stable branch, it also has access to a very large software repository. For those reasons, we will use Ubuntu LTS (Long Term Support) as the reference to Debian family distributions for this course.

## Some key facts about the Debian family are listed below

- The Debian family is upstream for Ubuntu, and Ubuntu is upstream for Linux Mint and others.
- Kernel version 5.19 is used in Ubuntu 22.04 LTS.
- It uses the DPKG-based APT package manager (using apt, apt-get, apt-cache, etc., which we cover in detail later) to install, update, and remove packages in the system.
- Ubuntu has been widely used for cloud deployments.
- While Ubuntu is built on top of Debian and is GNOME-based under the hood, it differs visually from the interface on standard Debian, as well as other distributions.

[The Device Directory /dev](Linux%20Distributation%201419c4fd2614806b8c66d40bec1df1c6/The%20Device%20Directory%20dev%201459c4fd261480b981ffcc9dbc4ae409.md)