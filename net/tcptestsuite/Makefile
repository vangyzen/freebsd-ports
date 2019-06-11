# $FreeBSD$

PORTNAME=	tcptestsuite
PORTVERSION=	0.0.3
CATEGORIES=	net ipv6

MAINTAINER=	gnn@FreeBSD.org
COMMENT=	Network stack test suite

LICENSE=	BSD2CLAUSE

RUN_DEPENDS=	packetdrill:net/packetdrill

USE_GITHUB=	yes
GH_ACCOUNT=	freebsd-net
GH_PROJECT=	tcp-testsuite
GH_TAGNAME=	f7a1844

NO_ARCH=	yes
NO_BUILD=	yes

do-install:
	${MKDIR} ${STAGEDIR}${DATADIR}
	${INSTALL_SCRIPT} ${WRKSRC}/run-all-tests ${STAGEDIR}${DATADIR}
	${INSTALL_SCRIPT} ${WRKSRC}/run-tests.sh ${STAGEDIR}${DATADIR}
	(cd ${WRKSRC} && \
		${COPYTREE_SHARE} "fast-open rcv-data-segments rcv-icmp snd-syn snippets socket-api state-event-engine" ${STAGEDIR}${DATADIR})

.include <bsd.port.mk>
