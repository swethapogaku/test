# test


-- create
CREATE TABLE T_LIFE_LINE_TIMES (
    F_ID BIGINT NOT NULL,
    F_STAKES_LOWER_LIMIT BIGINT NOT NULL,
    F_STAKES_UPPER_LIMIT BIGINT NOT NULL,
    F_LIFE_LINE_TIME BIGINT,
    PRIMARY KEY (F_ID, F_STAKES_LOWER_LIMIT, F_STAKES_UPPER_LIMIT)
);



-- insert
INSERT INTO T_LIFE_LINE_TIMES VALUES (1, 0, 5,0);
INSERT INTO T_LIFE_LINE_TIMES VALUES (1, 5, 20,20);
INSERT INTO T_LIFE_LINE_TIMES VALUES (2, 0, 5,20);
INSERT INTO T_LIFE_LINE_TIMES VALUES (2, 5, 10,30);


-- fetch 
SELECT * FROM T_LIFE_LINE_TIMES WHERE F_ID = 1;
===========================================================================================




-- create
CREATE TABLE T_NETWORK_POOL (
    F_NETWORK_POOL_ID TINYINT NOT NULL,
    F_DESC VARCHAR(50) NOT NULL,
    F_IS_ACTIVE VARCHAR(2) DEFAULT 'Y',
    F_GC_TYPE VARCHAR(10),
    PRIMARY KEY (F_NETWORK_POOL_ID)
);


-- insert
INSERT INTO T_NETWORK_POOL VALUES (0, 'SPATRON','Y','USD');
INSERT INTO T_NETWORK_POOL VALUES (1, 'Italia Liquidity','Y','EUR');
INSERT INTO T_NETWORK_POOL VALUES (2, 'Ontario Liquidity','Y','CAD');



-- fetch 
SELECT * FROM T_NETWORK_POOL WHERE F_NETWORK_POOL_ID = 1;



==========================================================================================





-- create
CREATE TABLE T_NETWORKS_POOL_MEMBERS (
    F_NETWORK_POOL_MEMBER_ID VARCHAR(10) NOT NULL,
    F_PRODUCT_ID VARCHAR(10) NOT NULL,
    F_IS_LOCAL_ONLY TINYINT,
    F_GC_TYPE VARCHAR(3),
    F_SHOW_ON_LOBBY TINYINT,
    F_NETWORK_POOL_ID TINYINT(2),
    F_REMOTE_POOL_ID TINYINT,
    PRIMARY KEY (F_NETWORK_POOL_MEMBER_ID, F_PRODUCT_ID)
);



-- insert
INSERT INTO T_NETWORKS_POOL_MEMBERS VALUES ('pr', 'POKER',0,'USD',1,0,0);
INSERT INTO T_NETWORKS_POOL_MEMBERS VALUES ('mj', 'POKER',0,'USD',1,4,0);
INSERT INTO T_NETWORKS_POOL_MEMBERS VALUES ('bi', 'POKER',0,'USD',1,1,0);





-- fetch 
SELECT * FROM T_NETWORKS_POOL_MEMBERS WHERE F_NETWORK_POOL_ID = 1;

==============================================================================
================================================================================

-- create
CREATE TABLE T_NETWORK_CURRENCY (
    F_NETWORK_POOL_ID BIGINT NOT NULL,
    F_NETWORK_CURRENCY VARCHAR(5) NOT NULL,
    F_PHASED_SETTLE_ACC VARCHAR(100),
    F_IS_ACTIVE VARCHAR(1),
    PRIMARY KEY (F_NETWORK_POOL_ID, F_NETWORK_CURRENCY)
);




-- insert
INSERT INTO T_NETWORK_CURRENCY VALUES (0,'USD','pp_ravindra','Y');





-- fetch 
SELECT * FROM T_NETWORK_CURRENCY WHERE F_NETWORK_POOL_ID = 0;


==============================================================

//create
CREATE TABLE t_platform_config (
    f_app_id TINYINT NOT NULL,
    f_key VARCHAR(100) NOT NULL,
    f_value VARCHAR(100),
    f_time DATE,
    PRIMARY KEY (f_key)
);

//insert 
INSERT INTO t_platform_config (f_app_id, f_key, f_value, f_time) 
VALUES 
(1, 'ENABLE_DIAMOND_BALANCE', 'TRUE', '2024-12-21 15:30:00'),
(2, 'US_FRONTENDS', 'nj,bj,mi,pv', '2024-12-22 09:15:45');


//fetch
select * from t_platform_config;

=================================================











=========================
