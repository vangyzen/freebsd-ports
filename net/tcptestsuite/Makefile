# $FreeBSD$

PORTNAME=	tcptestsuite
PORTVERSION=	0.0.4
CATEGORIES=	net ipv6

MAINTAINER=	gnn@FreeBSD.org
COMMENT=	Network stack test suite

LICENSE=	BSD2CLAUSE

RUN_DEPENDS=	packetdrill:net/packetdrill

USE_GITHUB=	yes
GH_ACCOUNT=	vangyzen	# TODO freebsd-net
GH_PROJECT=	tcp-testsuite
GH_TAGNAME=	c0066c2

NO_ARCH=	yes

pre-install:
	${MKDIR} -p ${STAGEDIR}${PREFIX}/tests/tcptestsuite

post-install:
	${MKDIR} ${STAGEDIR}${DATADIR}
	${INSTALL_SCRIPT} ${WRKSRC}/run-all-tests ${STAGEDIR}${DATADIR}
	${INSTALL_SCRIPT} ${WRKSRC}/run-tests.sh ${STAGEDIR}${DATADIR}
	(cd ${WRKSRC} && \
		${COPYTREE_SHARE} "fast-open rcv-data-segments rcv-icmp snd-syn snippets socket-api state-event-engine" ${STAGEDIR}${DATADIR})

.include <bsd.port.mk>
